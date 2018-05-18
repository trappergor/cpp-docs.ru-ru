---
title: Построение объектов потока вывода | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff3c924327c11d00dd9137a91ebd19ef7bdc9eaa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="constructing-output-stream-objects"></a>Построение объектов потока вывода

Если используются только стандартные объекты `cout`, `cerr` или `clog`, не требуется создавать поток вывода. Необходимо использовать конструкторы для:

- [конструкторов потока выходного файла](#vclrfoutputfilestreamconstructorsanchor1);

- [конструкторов потока выходной строки](#vclrfoutputstringstreamconstructorsanchor2).

## <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Конструкторы потока выходного файла

Вы можете создать поток выходного файла одним из двух следующих способов.

- Используйте конструктор по умолчанию, а затем вызовите функцию-член `open`.

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Укажите имя файла и флаги режима в вызове конструктора.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Конструкторы потока выходной строки

Чтобы создать поток выходной строки, можно использовать `ostringstream` следующим образом.

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

"Манипулятор" `ends` добавляет в строку необходимый завершающий нуль-символ.

## <a name="see-also"></a>См. также

[Потоки вывода](../standard-library/output-streams.md)<br/>
