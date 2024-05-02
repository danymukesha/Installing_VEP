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


## Modules, plugins, and other tools

Here are the necessary modules, plugins, and other tools to be installed first

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

- type _**y**_

  ![image](https://github.com/danymukesha/Installing_VEP/assets/45208254/25c61078-291d-476c-8e68-2517d039c409)

- Choose **472**

  ![image](https://github.com/danymukesha/Installing_VEP/assets/45208254/60439450-19ab-4b35-adfe-05a0a30394b2)
  - downloading https://ftp.ensembl.org/pub/release-111/variation/indexed_vep_cache/homo_sapiens_vep_111_GRCh38.tar.gz
  - unpacking homo_sapiens_vep_111_GRCh38.tar.gz
  - converting cache, this may take some time but will allow VEP to look up variants and frequency data much faster
  - use CTRL-C to cancel if you do not wish to convert this cache now (you may run convert_cache.pl later)

- type y

  ![image](https://github.com/danymukesha/Installing_VEP/assets/45208254/8ebf8412-466b-4656-b73c-60e3fc033f09)

FASTA files for the following species are available; which do you want (can specify multiple separated by spaces, "0" to install for species specified for cache download): 

![image](https://github.com/danymukesha/Installing_VEP/assets/45208254/b41d0ca3-2807-4034-b111-9ce1ee12db6d)

- type y

  ![image](https://github.com/danymukesha/Installing_VEP/assets/45208254/4d6eb253-1ca4-4d60-bd0d-7da2fe8cd9b8)



If you want to install cache in a particular mode, following this guidelines:
# Install cache for GRCh38, this needs to be a separate folder.
```sh
perl INSTALL.pl 
   --NO_TEST 
   --NO_HTSLIB 
   --AUTO alcf 
   --PLUGINS <NAME OF PLUGINS> 
   --CACHEDIR /mnt/xxx/repository/general/annotation/VEP/GRCh38 
   --PLUGINSDIR /mnt/xxx/repository/software/ensembl-vep/Plugins/GRCh38/ 
   --CONVERT 
   --SPECIES homo_sapiens_vep_104_GRCh38
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
sudo apt-get install libdbd-mysql-perl
```

To make sure you installed all necessary modules to run properly ./vep
```sh
sudo cpanm --installdeps . 
```

in the case you are using the remote databaset of Ensembl, 
You can test the connection to our database with the following MySQL command:

mysql -h ensembldb.ensembl.org -u anonymous


Save the case in which All Ensembl servers are not working. 
