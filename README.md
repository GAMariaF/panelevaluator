## Evaluere paneler feks ved nye prober

Ved feks bytte av probesett eller etter genlisetegjennomgang kjøres mosdepth for å generere dekning, deretter kjøres et R.script for å hente ut områder med for dårlig dekning som igjen brukes til å fylle ut en rapport.

1. Kopier over bams til mappen bams
2. Kjør mosdepth på de aktuelle bam`er for alle aktuelle paneler.
*   i run_mosdepth.nf sett inn følgende paramtre:
    *   params.panels -> mappen hvor panel-bedene ligger. eks: = "/illumina/runs_diag/prod_pipeline/refs/interval_files/filtexlister/2022/**.BED"
    *   params.bams -> mappen hvor bamene ligger. eks: = "./bams/*.bam"
    *   params.bais -> mappen hvor baiene ligger. eks: = "./bams/*.bai"
*   Kjør nextflow slik: ```nextflow run run_mosdepth.nf -c run_mosdepth.config```. Dette lagrer seg i results-mappen.
3. Åpne deretter evaluate.R og kjør gjennom den. Det generer filen validate_out.txt. Linjene i den filen kan limes inn i evaluering_av_HTS_paneler_ved_endring_av_probesammensetning-word-dokumentet.



