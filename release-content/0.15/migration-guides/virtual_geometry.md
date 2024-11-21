- Runtime
    - This feature now requires that your GPU supports `WgpuFeatures::SHADER_INT64_ATOMIC_MIN_MAX`.
    - `MeshletPlugin` now requires a `cluster_buffer_slots` field. Read the rustdoc for more details.
    - `MaterialMeshletMeshBundle` has been deprecated. Instead of using `Handle<MeshletMesh>` and `Handle<M: Material>` as components directly, use the `MeshletMesh3d` and `MeshMaterial3d` components.
- Asset Conversion
    - Regenerate your `MeshletMesh` assets, as the asset format has changed, and `MESHLET_MESH_ASSET_VERSION` has been bumped. Old assets are not compatible.
    - When using `MeshletMesh::from_mesh()`, the provided mesh must no longer have tangents as a vertex attribute.
    - When using `MeshletMesh::from_mesh()`, you must now supply a `vertex_position_quantization_factor` argument. Use `MESHLET_DEFAULT_VERTEX_POSITION_QUANTIZATION_FACTOR`, and adjust as needed. See the docs for more info.
- Misc
    - `MeshletMeshSaverLoad` has been split into `MeshletMeshSaver` and `MeshletMeshLoader`.
    - Renamed `MeshletMeshSaveOrLoadError` to `MeshToMeshletMeshConversionError`.
    - The `MeshletMeshSaveOrLoadError::SerializationOrDeserialization` enum variant has been removed.
    - Added `MeshToMeshletMeshConversionError::WrongFileType`, match on this variant if you match on `MeshToMeshletMeshConversionError`
    - `MeshletMesh` fields are now private.
    - The `Meshlet`, `MeshletBoundingSpheres`, and `MeshletBoundingSphere` types are now private.