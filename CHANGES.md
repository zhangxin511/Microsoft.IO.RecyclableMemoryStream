# Version 1.4.0

* Added netstandard2.0 target. There was an issue calling `GetBuffer` from a netstandard2.0 project, which would resolve to the netstandard1.4 target of RMS. netstandard1.4 doesn't support overriding `GetBuffer`, so you could hit `UnauthorizedAccessException`.
* A bug fix for `CopyToAsync`. It was copying the entire stream, but the expected behavior based on `System.IO.MemoryStream` is to copy from the current position.
* Some performance improvements to `CopyToAsync`. 

# Version 1.3.6

**Minor updates:**

* Override `CopyToAsync` to save some allocations.
* Apply `AllowPartiallyTrustedCallers` attribute to assembly

# Version 1.3.5

**Performance Improvements**

* `WriteByte` has been significantly optimized to be faster.
* `CheckDisposed`, which is called in many code paths, has similarly been optimized.

# Version 1.3.4

New API:
* `void WriteTo(Stream stream, int offset, int count)` -- Allows you to write a portion of the current stream to a destination stream without first having to call `GetBuffer`.

# Version 1.3.3

**Functionality**

- Added `RecyclableMemoryStreamManager.ThrowExceptionOnToArray`. Causes a `NotSupportedException` to be thrown if `RecyclableMemoryStream.ToArray` is called. Default is `false`.
- Added overloads of `RecyclableMemoryStreamManager.GetStream` that accept `Memory<byte>` arguments.

**Meta**

- Added changes.md to solution
- Regenerated API documentation for new XML comments and new APIs.

# Version 1.3.2
**Bug Fixes**

- Removed a buggy and unnecessary boundary check in Write methods.

**Performance**

- Removed LINQ iteration in some properties.
- Overloads of `Read`, `SafeRead`, and `Write` that accept `Span` arguments (.NET Core and .NET Standard targets only)

**Functionality**

- New buffer allocation strategy: exponential. Instead of linearly increasing large buffer sizes by a fixed multiple (say, 1MB), you can choose to have it increase exponentially in size, starting with smaller large buffers. This will allow you more efficient use of space, especially in smaller heap scenarios where you don't have gobs of memory to keep in a pool. We use this in Bing in some data centers that are more resource constrained than others.
- New targets for .NET Framework 4.6, .NET Standard 2.1
- Overload for `TryGetBuffer`, introduced in .NET Framework 4.6.
- Allow the Stream's GUID to be set explicitly

**Meta**

- Removed CBT build support files. Using dotnet.exe to build now.
- Added public key for delayed signing during build
- Consolidate and updated all NuGet package settings in the .csproj file.
- Added setting for generating a NuGet package for symbols (.snupkg)

# Version 1.2.0
- Bugs fixed when allocating very large streams.
- Concurrent methods for reading from a single stream added.
- Support for .NET 4.0 (without ETW instrumentation).
- It is now safe to call Dispose from multiple threads on the same object.

# Version 1.1.0
- Binaries on nuget.org are now signed through Microsoft.
- Some documentation enhancements and typo-cleanup.
- Some minor performance improvements.
- Fix behavior of `Dispose()` to be safe on double-dispose.

# Version 1.0.0
- Initial release.
