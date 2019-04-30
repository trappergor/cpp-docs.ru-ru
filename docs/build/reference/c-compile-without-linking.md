---
title: Параметр /c (компиляция без связывания)
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: bfe351daf43b913f10df74b1059ba98f7d5d657b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294854"
---
# <a name="c-compile-without-linking"></a>Параметр /c (компиляция без связывания)

Запрет автоматического вызова к СВЯЗИ.

## <a name="syntax"></a>Синтаксис

```
/c
```

## <a name="remarks"></a>Примечания

Компиляция с **/c** создает только OBJ-файлы. СВЯЗИ необходимо вызвать явным образом с необходимые файлы и параметры для выполнения этапа связывания построения.

Любой внутренний проект, созданный в среде разработки используется **/c** параметр по умолчанию.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

- Этот параметр не доступен из среды разработки.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.

## <a name="example"></a>Пример

Следующая команда создает объектные файлы FIRST.obj и SECOND.obj. THIRD.obj учитывается.

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

Чтобы создать исполняемый файл, необходимо вызвать ССЫЛКУ:

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
