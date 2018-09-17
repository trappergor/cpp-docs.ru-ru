---
title: -LN (Создание модуля MSIL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /LN
dev_langs:
- C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74c9ad6d8af797edb25a994f16334d40a3cbf910
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710857"
---
# <a name="ln-create-msil-module"></a>/LN (создание модуля MSIL)

Указывает, что манифест сборки не должен быть включен в выходной файл.

## <a name="syntax"></a>Синтаксис

```
/LN
```

## <a name="remarks"></a>Примечания

По умолчанию **/LN** не действует (манифест сборки вставляется в выходной файл).

Когда **/LN** используется, один из [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметры также должны использоваться.

Управляемая программа, которая не содержит метаданных сборки в манифесте, называется модуля. Если компиляция выполняется с [/c (компиляция без связывания)](../../build/reference/c-compile-without-linking.md) и **/LN**, укажите [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать выходной файл.

Вы можете создать модули, если вы хотите использовать подход на основе компонентов для создания сборок.  То есть можно создавать типы и компилировать их в модули.  Затем можно создать сборку из одного или нескольких модулей.  Дополнительные сведения о создании сборок из модулей, см. в разделе [.netmodule качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md) или [Al.exe (компоновщик сборок)](/dotnet/framework/tools/al-exe-assembly-linker).

Расширение файла по умолчанию для модуля — .netmodule.

В выпусках Visual C++ до Visual C++ 2005, модуль был создан с **/clr:noAssembly**.

Компоновщик Visual C++ в качестве входных данных принимает NETMODULE-файлы, и выходной файл, создаваемый компоновщиком будет сборки или .netmodule с не зависят от времени выполнения на любом из netmodules-файлы, которые были введены в компоновщик.  Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

- Укажите [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать выходной файл.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)