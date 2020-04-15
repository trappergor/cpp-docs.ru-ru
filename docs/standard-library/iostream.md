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
ms.openlocfilehash: 03afb777dc3926284cf0dc625e94a716ecdf5413
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375347"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Объявляет объекты, управляющие чтением из стандартных потоков и записью в них. Это включает в себя часто только заголовок вам нужно сделать входные данные и выход из программы СЗ.

## <a name="syntax"></a>Синтаксис

```cpp
#include <iostream>
```

> [!NOTE]
> В \<библиотеке> `#include <ios>`iostream используются `#include <streambuf>`, `#include <istream>`и `#include <ostream>` и заявления.

## <a name="remarks"></a>Remarks

Объекты можно разделить на две группы:

- [Cin](#cin), [cout,](#cout) [cerr,](#cerr)и [засорить](#clog) являются байт ориентированных, делать обычные байт-на-время переводов.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr) и [wclog](#wclog) — для двухбайтовых значений, они выполняют преобразования в двухбайтовые символы и из двухбайтовых символов, управление которыми осуществляется внутри программы.

После того как вы делаете определенные операции на потоке, такие как стандартный вход, вы не можете выполнять операции другой ориентации в одном потоке. Таким образом, программа не может работать взаимозаменяемо как на [цин](#cin) и [wcin,](#wcin)например.

Все объекты, заявленные в этом заголовке, имеют своеобразное свойство - можно предположить, \<что они построены до того, как какие-либо статические объекты вы определяете, в блоке перевода, который включает в себя>. Кроме того, можно предположить, что эти объекты не будут уничтожены перед деструктором для любых таких статических объектов, которые вы определяете. (Однако потоки вывода промываются во время завершения программы.) Таким образом, вы можете безопасно читать или писать на стандартные потоки до запуска программы и после завершения программы.

Эта гарантия не является универсальным, однако. Статический конструктор может вызвать функцию в другой записи преобразования. Названная функция не может предполагать, что объекты, заявленные в этом заголовке, были построены, учитывая неопределенный порядок, в котором переводческие блоки участвуют в статическом строительстве. Для использования этих объектов в таком контексте нужно сначала создать объект класса [ios_base::Init](../standard-library/ios-base-class.md#init).

### <a name="global-stream-objects"></a>Глобальные объекты потоков

|||
|-|-|
|[cerr](#cerr)|Указывает глобальный поток `cerr`.|
|[Cin](#cin)|Указывает глобальный поток `cin`.|
|[Засорить](#clog)|Указывает глобальный поток `clog`.|
|[cout](#cout)|Указывает глобальный поток `cout`.|
|[wcerr](#wcerr)|Указывает глобальный поток `wcerr`.|
|[вциом](#wcin)|Указывает глобальный поток `wcin`.|
|[wclog](#wclog)|Указывает глобальный поток `wclog`.|
|[wcout](#wcout)|Указывает глобальный поток `wcout`.|

### <a name="cerr"></a><a name="cerr"></a>серр

Объект `cerr` управляет выводом в буфер потока, связанного с объектом `stderr`, объявленным в \<cstdio>.

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Remarks

Этот объект управляет вставкой без буферизации в стандартный вывод ошибок в виде байтового потока. После создания объекта выражение `cerr.`[флаги](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) отлично от нуля, и `cerr.tie() == &cout`.

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

### <a name="cin"></a><a name="cin"></a>Cin

Указывает глобальный поток `cin`.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [istream](../standard-library/istream-typedefs.md#istream).

#### <a name="remarks"></a>Remarks

Объект контролирует получение данных из стандартного ввода, как потока байтов. После создания объекта вызов `cin.`[tie](../standard-library/basic-ios-class.md#tie) возвращает `&`[cout](#cout).

#### <a name="example"></a>Пример

В этом `cin` примере устанавливает бит сбоя в потоке, когда он натыкается на нечислоные символы. Программа очищает бит сбоя и удаляет недействительный символ из потока, чтобы продолжить.

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

### <a name="clog"></a><a name="clog"></a>Засорить

Указывает глобальный поток `clog`.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Remarks

Этот объект управляет вставкой с буферизацей в стандартный вывод ошибок в виде байтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `clog`.

### <a name="cout"></a><a name="cout"></a>Cout

Указывает глобальный поток `cout`.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Remarks

Этот объект управляет вставкой в стандартный вывод в виде байтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `cout`.

### <a name="wcerr"></a><a name="wcerr"></a>wcerr

Указывает глобальный поток `wcerr`.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Remarks

Этот объект управляет вставкой без буферизации в стандартный вывод ошибок в виде двухбайтового потока. После создания объекта выражение `wcerr.`[флаги](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) отлично от нуля.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcerr`.

### <a name="wcin"></a><a name="wcin"></a>вциом

Указывает глобальный поток `wcin`.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wistream](../standard-library/istream-typedefs.md#wistream).

#### <a name="remarks"></a>Remarks

Этот объект управляет извлечением из стандартного ввода в виде двухбайтового потока. После создания объекта вызов `wcin.`[tie](../standard-library/basic-ios-class.md#tie) возвращает `&`[wcout](#wcout).

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcin`.

### <a name="wclog"></a><a name="wclog"></a>wclog

Указывает глобальный поток `wclog`.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Remarks

Этот объект управляет вставкой с буферизацей в стандартный вывод ошибок в виде двухбайтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wclog`.

### <a name="wcout"></a><a name="wcout"></a>wcout

Указывает глобальный поток `wcout`.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Remarks

Этот объект управляет вставкой в стандартный вывод в качестве широкого потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcout`.

Экземпляры `CString`в операторе `wcout` необходимо привести к `const wchar_t*`, как показано в следующем примере.

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Дополнительные сведения см. в разделе [Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
