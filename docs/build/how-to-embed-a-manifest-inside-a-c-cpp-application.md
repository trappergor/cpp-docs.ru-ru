---
title: Практическое руководство. Внедрение манифеста в приложения C/C++
ms.date: 05/06/2019
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
ms.openlocfilehash: ee60620f2815bb20e2d0f3ecec768d99533437a9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220705"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Практическое руководство. Внедрение манифеста в приложения C/C++

Мы рекомендуем внедрить манифест приложения или библиотеки в конечный двоичный файл, так как это гарантирует нужная среда выполнения поведение в большинстве сценариев. По умолчанию Visual Studio пытается встроить манифест при построении проекта. Дополнительные сведения см. в разделе [Manifest Generation в Visual Studio](manifest-generation-in-visual-studio.md). Тем не менее если выполнить сборку приложения с помощью nmake, необходимо внести некоторые изменения в файл makefile. В этом разделе показано, как изменить файлы makefile, таким образом, чтобы он автоматически внедряет манифест в конечный двоичный файл.

## <a name="two-approaches"></a>Два подхода

Для внедрения манифеста в приложение или библиотека двумя способами.

- Если вы не выполняете инкрементное построение можно напрямую внедрить манифест с помощью командной строки, аналогичную следующей, в качестве шага после сборки:

   ```cmd
   mt.exe -manifest MyApp.exe.manifest -outputresource:MyApp.exe;1
   ```

   или

   ```cmd
   mt.exe -manifest MyLibrary.dll.manifest -outputresource:MyLibrary.dll;2
   ```

   Используйте 1 для EXE-файла и 2 для библиотеки DLL.

- Если вы выполняете инкрементное построение, выполните следующие действия:

   - Связывание двоичного файла для создания файла MyApp.exe.manifest.

   - Преобразуйте манифест в файл ресурсов.

   - Повторно инкрементная компоновка () для внедрения ресурса манифеста в двоичный файл.

В следующих примерах как изменить файл makefile, чтобы включить оба способа.

## <a name="makefiles-before"></a>Файлы makefile (раньше)

Рассмотрим сценарий nmake для MyApp.exe, простого приложения, построенного из одного файла.

```
# build MyApp.exe
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
```

Если этот сценарий выполняется без изменений в Visual Studio, он успешно создает MyApp.exe. Он также создает внешний файл манифеста MyApp.exe.manifest, который для использования операционной системой для загрузки зависимых сборок во время выполнения.

Скрипт nmake для MyLibrary.dll очень похожа:

```
# build MyLibrary.dll
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
```

## <a name="makefiles-after"></a>Файлы makefile (теперь)

Для построения со встроенными манифесты, вам придется внести четыре небольшие изменения в файлы makefile. Для проекта makefile MyApp.exe:

```
# build MyApp.exe
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_EXE)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

Для проекта makefile MyLibrary.dll:

```
# build MyLibrary.dll
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_DLL)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

Файлы makefile теперь включают два файла, которые выполняют реальной работы, makefile.inc и makefile.targ.inc.

Создайте makefile.inc и скопируйте в него следующее:

```
# makefile.inc -- Include this file into existing makefile at the very top.

# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
_VC_MANIFEST_INC=1
_VC_MANIFEST_BASENAME=__VC90.Debug

!else
CPPFLAGS=$(CPPFLAGS) /MD
_VC_MANIFEST_INC=0
_VC_MANIFEST_BASENAME=__VC90

!endif

####################################################
# Specifying name of temporary resource file used only in incremental builds:

!if "$(_VC_MANIFEST_INC)" == "1"
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res
!else
_VC_MANIFEST_AUTO_RES=
!endif

####################################################
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:

!if "$(_VC_MANIFEST_INC)" == "1"

#MT_SPECIAL_RETURN=1090650113
#MT_SPECIAL_SWITCH=-notify_resource_update
MT_SPECIAL_RETURN=0
MT_SPECIAL_SWITCH=
_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \
link $** /out:$@ $(LFLAGS)

!else

_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1

!endif

####################################################
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:

!if "$(_VC_MANIFEST_INC)" == "1"

_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \
    $(_VC_MANIFEST_BASENAME).auto.rc \
    $(_VC_MANIFEST_BASENAME).auto.manifest

!else

_VC_MANIFEST_CLEAN=

!endif

# End of makefile.inc
####################################################
```

Теперь создайте **makefile.targ.inc** и скопируйте в него следующее:

```
# makefile.targ.inc - include this at the very bottom of the existing makefile

####################################################
# Commands to generate initial empty manifest file and the RC file
# that references it, and for generating the .res file:

$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc

$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest
    type <<$@
#include <winuser.h>
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"
<< KEEP

$(_VC_MANIFEST_BASENAME).auto.manifest :
    type <<$@
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>
</assembly>
<< KEEP

# end of makefile.targ.inc
```

## <a name="see-also"></a>См. также

[Основные сведения о создании манифестов для программ на C/C++](understanding-manifest-generation-for-c-cpp-programs.md)
