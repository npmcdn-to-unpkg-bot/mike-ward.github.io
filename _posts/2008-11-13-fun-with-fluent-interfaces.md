---
layout: post  
title: 'Fun with Fluent Interfaces'
---
A while back I published a [helper class](/blog?p=b5b9e553-3e10-40ae-9f59-e38f1c50e2d6) that made routine argument checks one liners. For example:
    
    Throw.IfNullOrEmpty(name);

A friend of look at it and remarked that he liked it because it was a more [fluent interface](http://en.wikipedia.org/wiki/Fluent_interface). I had to look it up to find out exactly what he meant but the meaning is pretty clear just from the name of the pattern.

He then remarked that it would be even better if he could do something like this.
    
    Throw.If.name.IsNull;

I couldn’t see a way to do this in C# but the idea was interesting enough to toy around with a few ideas. Since the original Throw helpers were all static methods, the new helpers also should be static. With a bit of fiddling I came up with the following:
    
    using System;
    
    namespace FluentThrows
    {
        class Program
        {
            static void Main(string[] args)
            {
                Throw.If(args).IsNull();
                Throw.If(args.Length).Equals(7);
                Throw.If(args.Length).LessThan(2).GreaterThan(10);
                Throw.If(args[0]).IsNullOrEmpty();
                Throw.If(args[0]).NotEquals("my string");
            }
        }
    
        static class Throw
        {
            public static object If(object item)
            {
                return item;
            }
    
            public static IComparable If(IComparable item)
            {
                return item;
            }
    
            public static string If(string item)
            {
                return item;
            }
        }
    
        static class Ify
        {
            public static object IsNull(this object item)
            {
                if (item == null)
                    throw new ArgumentNullException();
    
                return item;
            }
    
            public static string IsNullOrEmpty(this string item)
            {
                if (string.IsNullOrEmpty(item))
                {
                    throw (item == null)
                        ? new ArgumentNullException()
                        : new ArgumentException("empty");
                }
    
                return item;
            }
    
            public static IComparable GreaterThan(this IComparable item, IComparable value)
            {
                if (item.CompareTo(value) > 0)
                    throw new ArgumentOutOfRangeException();
    
                return item;
            }
    
            public static IComparable LessThan(this IComparable item, IComparable value)
            {
                if (item.CompareTo(value) < 0)
                    throw new ArgumentOutOfRangeException();
    
                return item;
            }
    
            public static IComparable Equals(this IComparable item, IComparable value)
            {
                if (item.CompareTo(value) != 0)
                    throw new ArgumentOutOfRangeException();
    
                return item;
            }
    
            public static IComparable NotEquals(this IComparable item, IComparable value)
            {
                if (item.CompareTo(value) == 0)
                    throw new ArgumentOutOfRangeException();
    
                return item;
            }
        }
    }

It’s an interesting idea but I’m not sure if it’s much more useful than the [original version](/blog?p=b5b9e553-3e10-40ae-9f59-e38f1c50e2d6). Any thoughts?
