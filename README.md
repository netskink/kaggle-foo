# kaggle-foo
Stuff to do with kaggle

# install kaggle api

https://github.com/Kaggle/kaggle-api

## steps

1. install venv according to venv.md
2. Do this to install kaggle 
    1. mkdir secrets
    2. modify .gitignore to ignore secrets dir
    3. go to kaggle.com, login, go to accounts tab, create and download API token
    4. place token json file in secrets dir
    5. make sure json file is readable only by user 
        `$ chmod 0600 secrets/kaggle.json`
    6. set kaggle config env variable to point to json file 
        `$ export KAGGLE_CONFIG_DIR=/home/davis/progs/kaggle-foo/secrets`
    7. modify path to point to kaggle binary
        `$ export PATH=/home/davis/progs/kaggle-foo/venv/bin/:$PATH`
    8. ensure this command gives a proper response
        `$ kaggle`

## test to see if kaggle api can download sample data

```
$ GIT_HOME=$(git rev-parse --show-toplevel)
$ kaggle kernels output dansbecker/how-models-work -p /home/davis/progs/kaggle-foo/housing-prices
```

This should create a directory named housing-prices in the top level of this git repo.
In this directory should be a logfile.

eg.
```
$ ls $GIT_HOME/housing-prices
how-models-work.log
```

