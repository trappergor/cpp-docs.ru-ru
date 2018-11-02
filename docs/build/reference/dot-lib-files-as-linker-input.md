---
title: LIB-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
ms.openlocfilehash: 0bf791d682b66d9d0da968fb0bfd5229e912e84c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505359"
---
# <a name="lib-files-as-linker-input"></a>LIB-файлы в качестве входных файлов компоновщика

LINK принимает стандартные библиотеки COFF и библиотеки импорта COFF, каждый из которых обычно имеют расширение. lib. Стандартные библиотеки содержат объекты и создаются с помощью инструмента LIB. Библиотеки импорта содержат сведения об экспорте в другие программы и создаются ссылки при построении программы, содержащую экспорты, или с помощью средства LIB. Сведения об использовании LIB для создания стандартных или библиотеки импорта, см. в разделе [Справочник по LIB](../../build/reference/lib-reference.md). Дополнительные сведения об использовании ССЫЛОК для создания библиотеки импорта, см. в разделе [/DLL](../../build/reference/dll-build-a-dll.md) параметр.

Библиотека задается ссылку как аргумент имени файла или библиотеки по умолчанию. ССЫЛКА разрешении внешних ссылок, выполняя поиск сначала в библиотеках, которые указаны в командной строке, то по умолчанию библиотеки задано с помощью [/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) параметр, и затем в основной библиотеки с именем в OBJ-файлы. Если указан путь с именем библиотеки, LINK ищет библиотеки в этом каталоге. Если путь не указан, ссылка сначала выполнит поиск в каталоге, на котором установлены ссылки, а затем в любой каталогах, указанных в переменной среды LIB.

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Для добавления LIB-файлы в качестве входных данных компоновщика в среде разработки

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **ввода** страницы свойств в **компоновщика** папки.

1. Изменить **Дополнительные зависимости** свойство, добавляемое в LIB-файлы.

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Чтобы программно добавить LIB-файлы в качестве входных данных компоновщика

- См. в разделе [AdditionalDependencies](https://msdn.microsoft.com/library/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies.aspx).

## <a name="example"></a>Пример

Следующий пример показано, как создавать и использовать в LIB-файл. Сначала нужно создайте в LIB-файл:

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

И после этого следует скомпилировать этот пример с помощью LIB-файл, который вы только что создали.

```cpp
// lib_link_input_2.cpp
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp
__declspec(dllimport) int Test();
#include <iostream>
int main() {
   std::cout << Test() << std::endl;
}
```

```Output
213
```

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)