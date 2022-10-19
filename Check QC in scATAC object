
# This function let to observe the UMAP odf a scATAC object and its QC metrics  

ATAC.QC = function(obj){ 
  UmapObj = DimPlot(obj, reduction = 'umap', label = T, label.size = 7) + NoLegend() 
  
  Qc.1 = VlnPlot( 
    object = obj,
    features = 'pct_reads_in_peaks', 
    pt.size = 0) + geom_hline(yintercept = c(15, 40)) 
   
  Qc.2 = VlnPlot( # nolint 
    object = obj,
    features = 'peak_region_fragments', 
    pt.size = 0) + geom_hline(yintercept = c(3000, 20000)) 
   
  Qc.3 = VlnPlot( 
    object = obj,
    features = 'TSS.enrichment', 
    pt.size = 0) + geom_hline(yintercept = 2) 
  
  Qc.4 = VlnPlot( 
    object = obj,
    features = 'blacklist_ratio', 
    pt.size = 0) + geom_hline(yintercept = 0.05) 
   
  Qc.5 = VlnPlot( 
    object = obj,
    features = 'nucleosome_signal', 
    pt.size = 0) + geom_hline(yintercept = 4)
   
  #combine plots
  CombinePlots( 
    plots = list(UmapObj, Qc.1, Qc.2, Qc.3, Qc.4, Qc.5),
    legend = 'none') 
}
