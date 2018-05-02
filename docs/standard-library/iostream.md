---
title: '&lt;iostream&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 09/20/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
dev_langs:
- C++
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40b74dea33bbd4ed8436e8e90c35fb054974d0c7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Объявляет объекты, управляющие чтением из стандартных потоков и записью в них. Зачастую для ввода и вывода из программы на языке С++ нужно включить только заголовок.

## <a name="syntax"></a>Синтаксис

```cpp
#include <iostream>

```

## <a name="remarks"></a>Примечания

Объекты можно разделить на две группы:

- [cin](#cin), [cout](#cout), [cerr](#cerr) и [clog](#clog) — для байтовых значений, они выполняют обычную побайтовую передачу.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr) и [wclog](#wclog) — для двухбайтовых значений, они выполняют преобразования в двухбайтовые символы и из двухбайтовых символов, управление которыми осуществляется внутри программы.

После выполнения определенных операций с потоком, например, операции стандартного ввода, невозможно выполнять операции с другой ориентацией этого же потока. Поэтому, например, программа не может работать одинаково на [cin](#cin) и [wcin](#wcin).

Все объекты, объявленные в этом заголовке, имеют общее особое свойство: можно исходить из того, что они построены до любых определяемых вами статических объектов, в записи преобразования, включающей \<iostream>. Также можно предположить, эти объекты не уничтожаются до деструкторов для всех таких определяемых статических объектов. (При этом выходные потоки очищаются при завершении работы программы.) Поэтому можно безопасно читать из стандартных потоков или записывать в них до запуска программы и после ее завершения.

Но такая возможность есть не всегда. Статический конструктор может вызвать функцию в другой записи преобразования. Вызываемая функция не может исходить из того, что объекты, объявленные в этом заголовке, были построены, в силу неопределенности порядка, в котором записи преобразования участвуют в статической конструкции. Для использования этих объектов в таком контексте нужно сначала создать объект класса [ios_base::Init](../standard-library/ios-base-class.md#init).

### <a name="global-stream-objects"></a>Глобальные объекты потоков

|||
|-|-|
|[cerr](#cerr)|Указывает глобальный поток `cerr`.|
|[cin](#cin)|Указывает глобальный поток `cin`.|
|[clog](#clog)|Указывает глобальный поток `clog`.|
|[cout](#cout)|Указывает глобальный поток `cout`.|
|[wcerr](#wcerr)|Указывает глобальный поток `wcerr`.|
|[wcin](#wcin)|Указывает глобальный поток `wcin`.|
|[wclog](#wclog)|Указывает глобальный поток `wclog`.|
|[wcout](#wcout)|Указывает глобальный поток `wcout`.|

###  <a name="cerr"></a>  cerr

Объект `cerr` управляет выводом в буфер потока, связанного с объектом `stderr`, объявленным в \<cstdio>.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой без буферизации в стандартный вывод ошибок в виде байтового потока. После создания объекта выражение `cerr.` [флаги](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) отлично от нуля, и `cerr.tie() == &cout`.

#### <a name="example"></a>Пример

```cpp
// iostream_cerr.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void TestWide( )
{
   int i = 0;
   wcout << L"Enter a number: ";
   wcin >> i;
   wcerr << L"test for wcerr" << endl;
   wclog << L"test for wclog" << endl;
}

int main( )
{
   int i = 0;
   cout << "Enter a number: ";
   cin >> i;
   cerr << "test for cerr" << endl;
   clog << "test for clog" << endl;
   TestWide( );
}
```

###  <a name="cin"></a>  cin

Указывает глобальный поток `cin`.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [istream](../standard-library/istream-typedefs.md#istream).

#### <a name="remarks"></a>Примечания

Объект контролирует получение данных из стандартного ввода, как потока байтов. После создания объекта вызов `cin.` [tie](../standard-library/basic-ios-class.md#tie) возвращает `&` [cout](#cout).

#### <a name="example"></a>Пример

В этом примере `cin` устанавливает бит "fail" потока, если встречает символы, отличные от цифр. Затем программа очищает бит "fail" и удаляет некорректный символ из потока, затем продолжает выполнение.

```cpp
// iostream_cin.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
   int x;
   cout << "enter choice:";
   cin >> x;
   while (x < 1 || x > 4)
   {
      cout << "Invalid choice, try again:";
      cin >> x;
      // not a numeric character, probably
      // clear the failure and pull off the non-numeric character
      if (cin.fail())
      {
         cin.clear();
         char c;
         cin >> c;
      }
   }
}
```

```Output

2

```

###  <a name="clog"></a>  clog

Указывает глобальный поток `clog`.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой с буферизацей в стандартный вывод ошибок в виде байтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `clog`.

###  <a name="cout"></a>  cout

Указывает глобальный поток `cout`.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой в стандартный вывод в виде байтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `cout`.

###  <a name="wcerr"></a>  wcerr

Указывает глобальный поток `wcerr`.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой без буферизации в стандартный вывод ошибок в виде двухбайтового потока. После создания объекта выражение `wcerr.` [флаги](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) отлично от нуля.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcerr`.

###  <a name="wcin"></a>  wcin

Указывает глобальный поток `wcin`.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wistream](../standard-library/istream-typedefs.md#wistream).

#### <a name="remarks"></a>Примечания

Этот объект управляет извлечением из стандартного ввода в виде двухбайтового потока. После создания объекта вызов `wcin.` [tie](../standard-library/basic-ios-class.md#tie) возвращает `&` [wcout](#wcout).

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcin`.

###  <a name="wclog"></a>  wclog

Указывает глобальный поток `wclog`.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой с буферизацей в стандартный вывод ошибок в виде двухбайтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wclog`.

###  <a name="wcout"></a>  wcout

Указывает глобальный поток `wcout`.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой в стандартный вывод в качестве широкого потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcout`.

Экземпляры `CString`в операторе `wcout` необходимо привести к `const wchar_t*`, как показано в следующем примере.

```

    CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;
```

Дополнительные сведения см. в разделе [Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
