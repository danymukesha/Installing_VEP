# Installing_VEP
Installation of Variant Effect Predictor(VEP) 

1. Download
   ```sh
   git clone https://github.com/Ensembl/ensembl-vep.git
   ```

2. Install
   ```sh
   cd ensembl-vep
   perl INSTALL.pl
   ```

3. Test
   ```sh
   ./vep -i examples/homo_sapiens_GRCh38.vcf --cache
   ```



