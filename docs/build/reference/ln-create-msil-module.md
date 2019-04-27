---
title: /LN (создание модуля MSIL)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 18b0e72d50f328afc1f2856f833cec1aa7d46f30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176220"
---
# <a name="ln-create-msil-module"></a>/LN (создание модуля MSIL)

Указывает, что манифест сборки не должен быть включен в выходной файл.

## <a name="syntax"></a>Синтаксис

```
/LN
```

## <a name="remarks"></a>Примечания

По умолчанию **/LN** не действует (манифест сборки вставляется в выходной файл).

Когда **/LN** используется, один из [/CLR (компиляция CLR)](clr-common-language-runtime-compilation.md) параметры также должны использоваться.

Управляемая программа, которая не содержит метаданных сборки в манифесте, называется модуля. Если компиляция выполняется с [/c (компиляция без связывания)](c-compile-without-linking.md) и **/LN**, укажите [/NOASSEMBLY (Создание модуля MSIL)](noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать выходной файл.

Вы можете создать модули, если вы хотите использовать подход на основе компонентов для создания сборок.  То есть можно создавать типы и компилировать их в модули.  Затем можно создать сборку из одного или нескольких модулей.  Дополнительные сведения о создании сборок из модулей, см. в разделе [.netmodule качестве входных файлов компоновщика](netmodule-files-as-linker-input.md) или [Al.exe (компоновщик сборок)](/dotnet/framework/tools/al-exe-assembly-linker).

Расширение файла по умолчанию для модуля — .netmodule.

В выпусках Visual C++ до Visual C++ 2005, модуль был создан с **/clr:noAssembly**.

Компоновщик MSVC в качестве входных данных принимает NETMODULE-файлы и выходной файл, создаваемый компоновщиком будет сборки или .netmodule с не зависят от времени выполнения на любом из netmodules-файлы, которые были введены в компоновщик.  Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](netmodule-files-as-linker-input.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

- Укажите [/NOASSEMBLY (Создание модуля MSIL)](noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать выходной файл.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
