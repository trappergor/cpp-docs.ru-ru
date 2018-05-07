---
title: Построение объектов потока вывода | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: debc39987efffe149b8b7834ba5416027acadf4e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
