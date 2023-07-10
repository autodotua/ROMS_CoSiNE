# ROMS_CoSiNE

ROMS-CoSiNE基于[roms_kate](https://github.com/kshedstrom/roms)修改，[roms_kate](https://github.com/kshedstrom/roms)基于[ROMS](https://www.myroms.org/)修改。

## 修改日志

### 20230710

| 文件                                               | 修改目的                                                     |
| -------------------------------------------------- | ------------------------------------------------------------ |
| `Compilers/gfortran.m`                             | 将NETCDF库的死编码修改为环境变量                             |
| `Compilers\Linux-ifort.mk`                         | 之前的版本无法通过编译。使用最新版的ROMS编译参数进行替换     |
| `Compilers\Linux-pgi.mk`                           | 修改编译参数                                                 |
| `ROMS\External\varinfo.dat`                        | 将一些统一的`ocean_time`修改为单独的时间维度。修改湿度单位。修改一些CoSiNE变量的问题。 |
| `ROMS\Modules\mod_param.F`                         | 使未设置平流方案时自动设置为`MPDATA`，规避未能解决的无法设置CoSiNE变量平流方案的BUG |
| `ROMS\Nonlinear\Biology\biology.F`                 | 增加`bioUMaine.in`文件                                       |
| `ROMS\Nonlinear\Biology\umaine_inp.h`              | 修复`load_r`不接受二维参数导致无法通过编译的BUG              |
| `ROMS\Nonlinear\Biology\umaine_inp.h.modified.bak` | 另一投机取巧版本                                             |
| `ROMS\Nonlinear\step3d_t.F`                        | 之前的版本有BUG，比如河流无法流出示踪剂。使用最新版本ROMS的文件代替。 |
| `ROMS\Utility\def_info.F`                          | 修复输出nc文件中`bio_file`属性显示为乱码的BUG                |
