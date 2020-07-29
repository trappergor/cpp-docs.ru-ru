---
title: Построение объектов потока ввода
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: f281741979680fc03d3f96d2dbfbac6e1feefdea
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228314"
---
# <a name="constructing-input-stream-objects"></a>Построение объектов потока ввода

Если используется только стандартный объект `cin`, не требуется создавать входной поток. Вы должны создавать входной поток, если используете:

- [Конструкторы потока входного файла](#vclrfinputfilestreamconstructorsanchor8)

- [Конструкторы потока входной строки](#vclrfinputstringstreamconstructorsanchor9)

## <a name="input-file-stream-constructors"></a><a name="vclrfinputfilestreamconstructorsanchor8"></a> Конструкторы потока входного файла

Существует два способа создания потока входного файла.

- Используйте **`void`** конструктор аргумента, а затем вызовите `open` функцию члена:

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

## <a name="input-string-stream-constructors"></a><a name="vclrfinputstringstreamconstructorsanchor9"></a> Конструкторы потока входной строки

В конструкторах потока входной строки требуется адрес предварительно выделенного и предварительно инициализированного хранилища:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>См. также статью

[Входные потоки](../standard-library/input-streams.md)
