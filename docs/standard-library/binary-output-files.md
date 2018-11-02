---
title: Двоичные выходные файлы
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: 99445275a8f92622f451e8a88082dc2b28fb60b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615650"
---
# <a name="binary-output-files"></a>Двоичные выходные файлы

Потоки изначально были разработаны для текста, поэтому по умолчанию установлен режим вывода текста. В текстовом режиме символ перевода строки (шестнадцатеричное 10) расширяется возврата каретки (16-разрядная версия только). Расширение может вызвать проблемы, как показано ниже:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Можно предположить, что эта программа будет выводить байтовую последовательность {99, 0, 10, 0}; вместо этого она выводит {99, 0, 13, 10, 0}, что приводит к проблемам в программе, ожидающей ввод двоичных данных. Если требуются настоящие двоичные входные денные, в которых символы записаны непреобразованными, можно указать вывод двоичных данных с помощью аргумента openmode конструктора [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream):

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>См. также

[Потоки вывода](../standard-library/output-streams.md)<br/>
