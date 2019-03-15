---
title: /Zl (Опущенное по умолчанию имя библиотеки)
ms.date: 11/04/2016
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
ms.openlocfilehash: cb8083d874abe17add1d27096ebce143d03a04cf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809591"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Опущенное по умолчанию имя библиотеки)

Опускает имя библиотеки среды выполнения C по умолчанию из OBJ-файле. По умолчанию компилятор помещает имя библиотеки в OBJ-файл, чтобы перенаправить компоновщик в правильную библиотеку.

## <a name="syntax"></a>Синтаксис

```
/Zl
```

## <a name="remarks"></a>Примечания

Дополнительные сведения о библиотеке по умолчанию, см. в разделе [использование библиотеки времени выполнения](md-mt-ld-use-run-time-library.md).

Можно использовать **/Zl** для компиляции OBJ-файлы, которые планируется включить в библиотеку. Несмотря на то, что при пропуске названия библиотеки сохраняет только небольшой объем пространства для одном obj-файле, сохранить общее пространство важен в библиотеку, которая содержит много модулей объекта.

Этот параметр является дополнительным параметром. Этот параметр удаляет определенные поддержка библиотек времени выполнения C, необходимой для вашего приложения, в результате чего ошибки во время компоновки, если ваше приложение зависит от этой поддержки. При использовании этого параметра необходимо указать необходимые компоненты иным способом.

Используйте [/NODEFAULTLIB (пропуск библиотек)](nodefaultlib-ignore-libraries.md). Чтобы перенаправить компоновщик для пропуска ссылок на библиотеки в все OBJ-файлы.

Дополнительные сведения см. в разделе [Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md).

При компиляции с параметром **/Zl**, `_VC_NODEFAULTLIB` определен.  Пример:

```
// vc_nodefaultlib.cpp
// compile with: /Zl
void Test() {
   #ifdef _VC_NODEFAULTLIB
      int i;
   #endif

   int i;   // C2086
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **опустить имена библиотек по умолчанию** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
