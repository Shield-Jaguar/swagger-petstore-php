
# Pet

## Structure

`Pet`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?int` | Optional | - | getId(): ?int | setId(?int id): void |
| `category` | [`?Category`](../../doc/models/category.md) | Optional | - | getCategory(): ?Category | setCategory(?Category category): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `photoUrls` | `string[]` | Required | - | getPhotoUrls(): array | setPhotoUrls(array photoUrls): void |
| `tags` | [`?(Tag[])`](../../doc/models/tag.md) | Optional | - | getTags(): ?array | setTags(?array tags): void |
| `status` | [`?string (StatusEnum)`](../../doc/models/status-enum.md) | Optional | pet status in the store | getStatus(): ?string | setStatus(?string status): void |

## Example (as JSON)

```json
{
  "id": null,
  "category": null,
  "name": "name0",
  "photoUrls": [
    "photoUrls5",
    "photoUrls6",
    "photoUrls7"
  ],
  "tags": null,
  "status": null
}
```

