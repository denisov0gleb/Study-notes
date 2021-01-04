# SQLite API #


<!-- vim-markdown-toc GFM -->

* [Open database](#open-database)
* [Execute command](#execute-command)

<!-- vim-markdown-toc -->

## Open database ##

```c
int sqlite3_open(
  const char *filename,   /* Database filename (UTF-8) */
  sqlite3 **ppDb          /* OUT: SQLite db handle */
);

/*
 * return
 * 	0	if OK
 *		else error code
 */
```

Always need closing:

```c
sqlite3_close(filename);
```


## Execute command ##

```c
int sqlite3_exec(
  sqlite3*,                                  /* Opened database */
  const char *sql,                           /* SQL sentence to be evaluated (UTF-8) */
  int (*callback)(void*,int,char**,char**),  /* Callback function */
  void *,                                    /* 1st argument to callback */
  char **errmsg                              /* Error message written here */
);
```
