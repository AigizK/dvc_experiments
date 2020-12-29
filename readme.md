#step 1

dvc init

#step 2

mkdir data

dvc get https://github.com/iterative/dataset-registry \
> get-started/data.xml -o data/data.xml

dvc add data/data.xml

#step 3

create a folder in google drive and copy id from url

add a remote dvc storage
dvc remote add -d storage gdrive://1P00000000tXpFOuO2Mg4sJQXsnFZ9z0w

#step 4

pip install 'dvc[gdrive]'

dvc push

open the link with google drive auth and give permissions for DVC
