# libvirtulink
Create symlinks for only a single application

# How to use
Virtual symlinks can be created by using the `LIBVL_FIND` and `LIBVL_REPLACE` variables. The `LIBVL_REPLACE` is the path that LIBVL_FIND points to (like a symlink)
### Example :
```
LIBVL_FIND=/home/SuicSoft/Pictures/RandomStuff/
LIBVL_REPLACE=/home/SuicSoft/Pictures/TheNewPathForRandomStuff/
LD_PRELOAD=/path/to/libvirtulink/lib your-program
```
If the program trys to access any files from **RandomStuff** they will be redirected to  **TheNewPathForRandomStuff** similar to how a symlink works. **libvirtulink** can also be used on folders that you do not have permission to edit (such as the **/usr** folder) and a use for this would be to create a portable application from a binary (compiled with **/usr** as the prefix and using libvirtulink to make **/usr** point to another folder) without recompiling it.

## NOTE : Currently the application only overrides open(). I am looking for a proper way to override all file calls without implementing every single file call.
