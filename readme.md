#step 1

dvc init

#step 2

mkdir data

dvc get https://github.com/iterative/dataset-registry \
> get-started/data.xml -o data/data.xml

dvc add data/data.xml
