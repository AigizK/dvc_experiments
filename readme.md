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

#step 5

we can remove data and cache and run `dvc pull` for restore data

rm -f data/data.xml
rm -rf .dvc/cache

dvc pull

#step 6

modify dataset

(venv) ➜  dvc_experiments git:(master) cp data/data.xml /tmp/data.xml
(venv) ➜  dvc_experiments git:(master) cat /tmp/data.xml >> data/data.xml

dvc add data/data.xml
dvc push
