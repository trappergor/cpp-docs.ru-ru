---
title: Построение объектов входного потока | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7066ffe50dc76c26528e7bfcd3dc9e9778e1473a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842876"
---
# <a name="constructing-input-stream-objects"></a>Построение объектов потока ввода

Если используется только стандартный объект `cin`, не требуется создавать входной поток. Вы должны создавать входной поток, если используете:

- [Конструкторы потока входного файла](#vclrfinputfilestreamconstructorsanchor8)

- [Конструкторы потока входной строки](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> Конструкторы потока входного файла

Существует два способа создания потока входного файла.

- Используйте конструктор аргумента `void`, а затем вызовите функцию-член `open`:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Укажите имя файла и флаги режима в вызове конструктора, тем самым открывая файл во время процесса построения:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> Конструкторы потока входной строки

В конструкторах потока входной строки требуется адрес предварительно выделенного и предварительно инициализированного хранилища:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
