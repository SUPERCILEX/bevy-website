The `ZIndex` enum has been split into two separate components `ZIndex` (which replaces `ZIndex::Local`) and `GlobalZIndex` (which replaces `ZIndex::Global`). An entity can have both a `ZIndex` and `GlobalZIndex`, in comparisons `ZIndex` breaks ties if two `GlobalZindex` values are equal.