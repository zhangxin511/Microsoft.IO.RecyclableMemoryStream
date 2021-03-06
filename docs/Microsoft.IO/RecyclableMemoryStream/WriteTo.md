# RecyclableMemoryStream.WriteTo method (1 of 3)

Synchronously writes this stream's bytes to the argument stream.

```csharp
public override void WriteTo(Stream stream)
```

| parameter | description |
| --- | --- |
| stream | Destination stream |

## Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | stream is null |

## Remarks

Important: This does a synchronous write, which may not be desired in some situations

## See Also

* class [RecyclableMemoryStream](../RecyclableMemoryStream.md)
* namespace [Microsoft.IO](../../Microsoft.IO.RecyclableMemoryStream.md)

---

# RecyclableMemoryStream.WriteTo method (2 of 3)

Synchronously writes this stream's bytes, starting at offset, for count bytes, to the argument stream.

```csharp
public void WriteTo(Stream stream, int offset, int count)
```

| parameter | description |
| --- | --- |
| stream | Destination stream |
| offset | Offset in source |
| count | Number of bytes to write |

## Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | stream is null |
| ArgumentOutOfRangeException | Offset is less than 0, or offset + count is beyond this stream's length. |

## See Also

* class [RecyclableMemoryStream](../RecyclableMemoryStream.md)
* namespace [Microsoft.IO](../../Microsoft.IO.RecyclableMemoryStream.md)

---

# RecyclableMemoryStream.WriteTo method (3 of 3)

Synchronously writes this stream's bytes, starting at offset, for count bytes, to the argument stream.

```csharp
public void WriteTo(Stream stream, long offset, long count)
```

| parameter | description |
| --- | --- |
| stream | Destination stream |
| offset | Offset in source |
| count | Number of bytes to write |

## Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | stream is null |
| ArgumentOutOfRangeException | Offset is less than 0, or offset + count is beyond this stream's length. |

## See Also

* class [RecyclableMemoryStream](../RecyclableMemoryStream.md)
* namespace [Microsoft.IO](../../Microsoft.IO.RecyclableMemoryStream.md)

<!-- DO NOT EDIT: generated by xmldocmd for Microsoft.IO.RecyclableMemoryStream.dll -->
