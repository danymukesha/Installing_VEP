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




necessary modules to be installed first"

```sh
wget https://www.cpan.org/modules/by-module/DBI/DBI-1.643.tar.gz
```

Once you download the DBI module file, you will need to extract (it is compressed) and compile it, as follows:

Unpack the archive
```sh
tar xvfz DBI-1.15.tar.gz
```
Generate the "Makefile":
```sh
cd     DBI-1.15
perl Makefile.PL
```
Make the installable files:
```sh
make
```
Test the new files:
```sh
make test
```
Install the modules and the DBI program into the configured Perl library and binary directories.
```sh
make install
```

```sh
sudo cpan App::cpanminus1
sudo cpan Archive::Zip
sudi span Data::ShowTable
sudo cpan DBD::mysql
sudo cpan Bio::EnsEMBL::Registry
sudo cpan Bio::EnsEMBL
sudo cpan Module::Build
sudo cpan LWP::Simple HTTP::Tiny
```

To make sure you installed all necessary modules to run properly ./vep
```sh
cpanm --installdeps . 
```
