# Milestones (honest status)

| Capability | Status | Evidence |
|---|---|---|
| Native GeoTIFF reader/writer, CRS classification (Moon/Earth/unknown), geometry | Implemented + tested | tests/test_geo_terrain.py |
| Immutable originals, SHA-256, manifests, event log, tamper detection | Implemented + tested | test_pipeline.TestWorkspace |
| Evidence-based dataset identification + analyst confirmation (filename never sufficient) | Implemented + tested | test_core.TestIdentify, TestWorkspace |
| Site identity from project, not filename (Site01 file -> Site 11 retained) | Implemented + tested | test_pipeline.TestWorkspace |
| Raster validation (16 checks), grid compatibility, resample with oversampling flag | Implemented + tested | test_core.TestValidate, test_geo_terrain.TestGeo |
| Slope (Horn, stereographic scale-corrected, baseline), aspect, curvature, relief, roughness | Implemented + tested | TestTerrain |
| Crater CANDIDATE detection (LoG, human review) | Partially implemented (synthetic craters only; diameter +/-35% by morphology) | TestTerrain.test_crater_detection_vs_truth |
| Illumination, Earth visibility, solar incidence with terrain horizon + ephemeris | Implemented + tested (DEM-only horizon; no penumbra/thermal) | TestEnvironment, TestEphemeris |
| Hard gates, statuses, weighted scoring, comparability, Monte Carlo/normalisation/OAT sensitivity | Implemented + tested | TestScoring |
| Single-site pipeline, JSON/CSV/PDF reports, GeoTIFF products, OBJ/PLY mesh | Implemented + tested | TestPipeline, TestMesh |
| Reproducibility (identical derived SHA-256 across runs) | Implemented + tested | TestPipeline.test_reproducibility |
| Large raster (2500x2500) and corrupt/truncated files | Tested at moderate scale only | TestWorkspace |
| Streamlit console (14 modules) | Partially implemented: runs against stub Streamlit only; never opened in a real browser | test_ui_smoke |
| Interactive 3D (Plotly Surface, overlays, vertical exaggeration) | Partially implemented: code written, Plotly not installed here, not executed | ui/app.py |
| Time-linked 3D lighting (shadow overlay driven by the time slider) | Not started (instant shadow maps exist in Environmental Analysis; not wired into 3D) | environment.instant_state |
| GLB export | Blocked: needs optional trimesh (not installed); raises a clear error | meshio.write_glb |
| Colab notebook; Google Drive storage | Partially implemented: notebook written, never run in Colab | notebooks/ |
| Windows/Linux install instructions | Written; Linux sandbox only, Windows untested | README.md |
| Dependency locking | Partial: sandbox versions recorded; true lock needs network | requirements-lock-sandbox.txt |
| PDS3/PDS4/ISIS readers | Not started (adapter slots + honest status table exist) | workspace.ADAPTERS |
| Vector (GeoJSON/Shapefile/GeoPackage), CSV, NetCDF, HDF5, COG optimisation | Blocked/Not started (geopandas, xarray, h5py not available offline) | workspace.ADAPTERS |
| Mosaicking, vector rasterisation, DEM reprojection pipeline | Not started (point resampling exists) | geo.resample |
| Thermal model; radiation; micrometeoroid; relay visibility; resource accessibility | Not started (ingest-only or absent; never inferred) | factors.py |
| Rock abundance, ice, hydrogen, volatiles, regolith | Ingest-only: no scoring method; NOT ASSESSED unless a calibrated product exists | factors.py |
| Landing-zone (footprint) identification and zone-level gates | Not started: site-level statistics over the whole DEM only | pipeline.py |
| Validation against real lunar reference datasets | Not started: no real data supplied; Apollo Sun angles checked against recalled values only | VALIDATION_REPORT.md |
