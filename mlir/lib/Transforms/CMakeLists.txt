add_subdirectory(Utils)

add_mlir_library(MLIRTransforms
  AffineDataCopyGeneration.cpp
  AffineLoopInvariantCodeMotion.cpp
  Canonicalizer.cpp
  CSE.cpp
  DialectConversion.cpp
  Inliner.cpp
  LocationSnapshot.cpp
  LoopCoalescing.cpp
  LoopFusion.cpp
  LoopInvariantCodeMotion.cpp
  LoopTiling.cpp
  LoopUnrollAndJam.cpp
  LoopUnroll.cpp
  MemRefDataFlowOpt.cpp
  OpStats.cpp
  PipelineDataTransfer.cpp
  SimplifyAffineStructures.cpp
  StripDebugInfo.cpp
  SymbolDCE.cpp
  Vectorize.cpp
  ViewOpGraph.cpp
  ViewRegionGraph.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Transforms

  DEPENDS
  MLIRStandardOpsIncGen
  )

target_link_libraries(MLIRTransforms
  PUBLIC
  MLIRAffineOps
  MLIRAnalysis
  MLIRLoopLikeInterface
  MLIRLoopOps
  MLIRPass
  MLIRTransformUtils
  MLIRVector
  )
