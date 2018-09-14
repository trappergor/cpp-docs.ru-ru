---
title: Ошибка компилятора C2857 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2857
dev_langs:
- C++
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49e94e12b4cdf07d9f7fe74dd481bbc032a937eb
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601383"
---
# <a name="compiler-error-c2857"></a>Ошибка компилятора C2857

> "#include" инструкция, указанная с параметром/Yc*filename* параметр командной строки не найден в исходном файле

[/Yc](../../build/reference/yc-create-precompiled-header-file.md) параметр указывает имя включаемого файла, которая не включена в исходный файл, при компиляции.

## <a name="remarks"></a>Примечания

При использовании **/Yc**<em>filename</em> должен включать параметр на исходном файле, чтобы создать файл предкомпилированного заголовка (PCH), что исходный файл *filename* файл заголовка. Каждый файл, включенный файл источника, вплоть до указанного *filename*, включается в PCH-файл. В других файлах исходного кода, скомпилированные с помощью **/Yu**<em>filename</em> файл параметр, чтобы использовать предкомпилированный заголовок, включаемый из *filename* должно быть в первой строке файла, не являющихся комментариями. Компилятор игнорирует любого элемента в файле исходного кода перед этой include.

Эта ошибка может быть вызвана `#include "filename"` оператор в блоке условной компиляции, который не компилируется в файле исходного кода для PCH.

## <a name="example"></a>Пример

В обычном режиме один исходный файл в проекте используется в качестве источника PCH-файл и один файл заголовка используется в качестве заголовка PCH-файл. Стандартный файл заголовка PCH имеет все заголовки библиотеки, используемые в проекте, но не локальных заголовков, на стадии разработки. В этом образце заголовка PCH-файл с именем *my_pch.h*.

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

Исходный файл PCH компилируется с помощью **/Yc**<em>my_pch.h</em> параметр. Если компилятор не находит включаемый этого файла заголовка PCH-ФАЙЛ, он создает C2857:

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

Чтобы использовать этот файл PCH, исходные файлы, должны компилироваться с помощью **/Yu**<em>my_pch.h</em> параметр. Файл заголовка PCH-ФАЙЛ должен быть включен сначала в исходных файлах, использующих предкомпилированного Заголовка:

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```