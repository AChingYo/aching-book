# Preprocessor 技巧

## Using preprocessor to check if header is existed or not

最近實務上需要開發一個客製化的Kernel module給 Linux OS based 的產品，並決定用一個獨立的Git 專案做版本控制，但若Kernel module本身需要做到支援不同版本的Linux平台，勢必會遇到不同的Linux branch 下kernel header不一致，此時就需要透過C 的Preprocessor編譯期間去確定Header是否存在去編譯不同的程式碼。

```c
// Note the two possible file name string formats.
#if __has_include("myinclude.h") && __has_include(<stdint.h>)
# include "myinclude.h"
#endif
```

#### References

{% embed url="https://clang.llvm.org/docs/LanguageExtensions.html\#langext-has-include" %}

{% embed url="https://isocpp.org/std/standing-documents/sd-6-sg10-feature-test-recommendations" %}



