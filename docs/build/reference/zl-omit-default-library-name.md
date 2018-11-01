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
ms.openlocfilehash: ba30efd76e94749dd261f3528535d674b5e155e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621914"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Опущенное по умолчанию имя библиотеки)

Опускает имя библиотеки среды выполнения C по умолчанию из OBJ-файле. По умолчанию компилятор помещает имя библиотеки в OBJ-файл, чтобы перенаправить компоновщик в правильную библиотеку.

## <a name="syntax"></a>Синтаксис

```
/Zl
```

## <a name="remarks"></a>Примечания

Дополнительные сведения о библиотеке по умолчанию, см. в разделе [использование библиотеки времени выполнения](../../build/reference/md-mt-ld-use-run-time-library.md).

Можно использовать **/Zl** для компиляции OBJ-файлы, которые планируется включить в библиотеку. Несмотря на то, что при пропуске названия библиотеки сохраняет только небольшой объем пространства для одном obj-файле, сохранить общее пространство важен в библиотеку, которая содержит много модулей объекта.

Этот параметр является дополнительным параметром. Этот параметр удаляет определенные поддержка библиотек времени выполнения C, необходимой для вашего приложения, в результате чего ошибки во время компоновки, если ваше приложение зависит от этой поддержки. При использовании этого параметра необходимо указать необходимые компоненты иным способом.

Используйте [/NODEFAULTLIB (пропуск библиотек)](../../build/reference/nodefaultlib-ignore-libraries.md). Чтобы перенаправить компоновщик для пропуска ссылок на библиотеки в все OBJ-файлы.

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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **опустить имена библиотек по умолчанию** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)