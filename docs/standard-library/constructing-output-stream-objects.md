---
title: Построение объектов потока вывода
ms.date: 11/04/2016
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
ms.openlocfilehash: 7da7d9dd0fae3ce3fa21ecd774f88643dca49c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212005"
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
