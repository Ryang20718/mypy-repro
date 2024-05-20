# MYPY following imports on some modules even though mypy.ini skips the imports

# To repro
1. `pip install -r requirements.txt`
2. mypy --timing-stats=out.txt --no-incremental example/c.py 
3. we see out.txt contains timing from importing numpy which isn't expected?
```bash
numpy 64081
numpy._pytesttester 320
numpy._typing._callable 5586
numpy.core 127
numpy.core._asarray 722
numpy.core._internal 710
numpy.core._type_aliases 428
numpy.core._ufunc_config 504
numpy.core.arrayprint 1504
numpy.core.defchararray 3521
..
<snip>
```
