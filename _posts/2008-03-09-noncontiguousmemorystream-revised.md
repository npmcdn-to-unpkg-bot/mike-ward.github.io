---
layout: post  
title: 'NonContiguousMemoryStream Revised'
---
[Earlier I wrote about a class I designed to combat large heap fragmentation issues with memory streams](http://mike-ward.net/2007/12/27/noncontiguousmemorystream-in--net/). I've updated the class to correct a bug I recently discovered in the read routine. I've also published the entire solution with additional unit tests.

`MemoryStreams` are darn handy little buggers for caching away results from serialization and file copy operations. However, there's a dark side in that `MemoryStreams` can create additional memory pressure, particularly when stream sizes grow in excess of about 85K. At that point, the .NET run-time allocates from the large memory heap. This heap does not compact like the small memory heap and can lead to fragmentation. Often, this can cause `OutOfMemoryExceptions` long before physical memory is exhausted.

No amount of garbage collection will reclaim this memory due to a quirk in the .NET memory management. The `NonContiguousMemoryStream` offered here mitigates this issue by using a memory store made of smaller buffers. Since the large heap is never touched, the run-time can do a better job of compacting and reclaiming memory.

My informal testing shows that `NonContiguousMemoryStream` can run approximately 4 times longer than conventional memory streams before exhausting memory. The trade off is slightly lower performance owing to the overhead of managing multiple buffers. Also, the minimum size of a `NonContiguousMemoryStream` is 64K due to the fixed buffer size. You'll want to make certain of your needs before resorting to this hammer. I'm planning to write a hybrid version that will perform like a regular `MemoryStream` for small sizes and switch to `NonContiguousMemoryStream` as the stream grows.

[Bloget](/bloget) uses this class as well so I'll be issuing a second Beta to cover this and other issues. I've been living with this bug for a few months in Bloget without incident so the bug's affect is somewhat of a corner case. Still it's a concern and should be noted (and fixed).

`NonContiguousMemoryStream` is available on the [Downloads](/downloads) page.
    