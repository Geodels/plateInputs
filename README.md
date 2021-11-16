# plateInputs: extracting plate reconstruction and paleo-elevation forcing for goSPL model

## plateInputs

**plateInputs** is an open source, GPL-licensed library providing a  Python-based framework to build forcing conditions when running `goSPL` global model using specific plate reconstruction and paleo-elevation models.

### Dependencies

#### pygplates

#### PnetCDF
The code can be downloaded [here](https://parallel-netcdf.github.io/wiki/Download.html).
To install for this code usage, the following steps and configurations will do:
```sh
$ wget https://parallel-netcdf.github.io/Release/pnetcdf-1.12.1.tar.gz
$ tar -xf pnetcdf-1.12.1.tar.gz
$ cd pnetcdf-1.12.1
$ mkdir build
$ cd build
# Replace <YourInstalationDir> with a new directory to install PnetCDF to
# Replace <YourMpiInstalationDir> for the folder containing the MPI instalation
$ ../configure --prefix=<YourInstalationDir> --with-mpi=<YourMpiInstalationDir> CC=mpicc --enable-shared
$ make -j
$ make install
```

#### Parallel dbscan

https://github.com/pedro-ricardo/Parallel-DBSCAN


#### Others

Then `cd` to the repository and do a
```bash
python3 setup.py install --user
```


### Running plateInputs

```python
from plateInputs.model import Model as sim

# Reading input file
model = sim('inputearth.yml', verbose=True)

# Running
model.runProcesses()

```
