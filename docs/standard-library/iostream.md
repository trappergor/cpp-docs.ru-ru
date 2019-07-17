---
title: '&lt;iostream&gt;'
ms.date: 09/20/2017
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
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
ms.openlocfilehash: fa90a861194275d8c82a407e2ca8db6e757aab35
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245229"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Объявляет объекты, управляющие чтением из стандартных потоков и записью в них. Чаще всего это включить только заголовок, вам потребуется входные и выходные данные из C++ программы.

## <a name="syntax"></a>Синтаксис

```cpp
#include <iostream>
```

> [!NOTE]
> \<Iostream > Библиотека использует `#include <ios>`, `#include <streambuf>`, `#include <istream>`, и `#include <ostream>` инструкций.

## <a name="remarks"></a>Примечания

Объекты можно разделить на две группы:

- [CIN](#cin), [cout](#cout), [cerr](#cerr), и [clog](#clog) — для байтовых, выполнив обычную передачу байтов во времени.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr) и [wclog](#wclog) — для двухбайтовых значений, они выполняют преобразования в двухбайтовые символы и из двухбайтовых символов, управление которыми осуществляется внутри программы.

После этого определенных операций с потоком, например стандартного потока ввода, не поддерживается операциями с другой ориентацией в одном потоке. Таким образом, программа не может работать одинаково на обоих [cin](#cin) и [wcin](#wcin), например.

Все объекты, объявленные в этой общей папке заголовка общее особое свойство, можно предположить, они все создан, прежде чем все статические объекты, определить, в записи преобразования, включающий \<iostream >. Одинаково можно предположить, что эти объекты не уничтожаются до деструкторов для таких определяемых статических объектов. (При этом выходные потоки очищаются при завершении работы программы.) Поэтому можно безопасно читать из стандартных потоков или записывать в них до запуска программы и после ее завершения.

Эта гарантия не является универсальной, тем не менее. Статический конструктор может вызвать функцию в другой записи преобразования. Вызываемая функция нельзя предполагать, что объекты, объявленные в этом заголовке, были построены, в силу неопределенности порядка, в котором записи преобразования единиц участвовать в статической конструкции. Для использования этих объектов в таком контексте нужно сначала создать объект класса [ios_base::Init](../standard-library/ios-base-class.md#init).

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

###  <a name="cerr"></a> cerr

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

###  <a name="cin"></a> CIN

Указывает глобальный поток `cin`.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [istream](../standard-library/istream-typedefs.md#istream).

#### <a name="remarks"></a>Примечания

Объект контролирует получение данных из стандартного ввода, как потока байтов. После создания объекта вызов `cin.` [tie](../standard-library/basic-ios-class.md#tie) возвращает `&` [cout](#cout).

#### <a name="example"></a>Пример

В этом примере `cin` задает бит "fail" потока при себя алфавитно цифровые символы. Программа очищает бит fail и удаляет некорректный символ из потока, чтобы продолжить.

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

###  <a name="clog"></a> clog

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

###  <a name="cout"></a> cout

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

### <a name="wcerr"></a> wcerr

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

### <a name="wcin"></a> wcin

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

### <a name="wclog"></a> wclog

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

### <a name="wcout"></a> wcout

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
