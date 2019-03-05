---
title: Класс CDumpContext
ms.date: 11/04/2016
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
ms.openlocfilehash: a5b53ced4e20c920aab8e7ebcda3e3f6f8798ba5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258623"
---
# <a name="cdumpcontext-class"></a>Класс CDumpContext

Поддерживает ориентированных на поток диагностические данные в форме человекочитаемого текста.

## <a name="syntax"></a>Синтаксис

```
class CDumpContext
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CDumpContext::CDumpContext](#cdumpcontext)|Создает объект `CDumpContext`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CDumpContext::DumpAsHex](#dumpashex)|Выводит указанный элемент в шестнадцатеричном формате.|
|[CDumpContext::Flush](#flush)|Удаляет все данные в буфере контекста дампа.|
|[CDumpContext::GetDepth](#getdepth)|Возвращает целое число, соответствующее глубину дампа.|
|[CDumpContext::HexDump](#hexdump)|Создает дамп байтов, содержащихся в массиве в шестнадцатеричном формате.|
|[CDumpContext::SetDepth](#setdepth)|Задает глубину дампа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CDumpContext::operator &lt;&lt;](#operator_lt_lt)|Вставляет переменные и объекты в контекст дампа.|

## <a name="remarks"></a>Примечания

`CDumpContext` не имеет базового класса.

Можно использовать [afxDump](diagnostic-services.md#afxdump), предварительно объявленных `CDumpContext` объекта, для большей части вашего формирование дампа. `afxDump` Объект доступен только в отладочной версии библиотеки Microsoft Foundation Class.

Некоторые из памяти [диагностические службы](../../mfc/reference/diagnostic-services.md) использовать `afxDump` для свои выходные данные.

В среде Windows, выходные данные из предварительно определенных `afxDump` объекта, концептуально сходная с `cerr` потока, направляется к отладчику через функцию Windows `OutputDebugString`.

`CDumpContext` Класс имеет перегруженный Вставка ( **<<**) оператор для `CObject` указатели, которые создает дамп данных объекта. Если вам требуется формат дампа пользовательского производного объекта, переопределяют [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Большинство классов Microsoft Foundation реализуют переопределенный `Dump` функция-член.

Классы, которые не являются производными от `CObject`, такие как `CString`, `CTime`, и `CTimeSpan`, имеют свои собственные перегруженных `CDumpContext` операторы вставки, как часто используемые структуры, такие как `CFileStatus`, `CPoint`, и `CRect`.

Если вы используете [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) или [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос в реализации класса, затем `CObject::Dump` выводит имя вашей `CObject`-производного класса. В противном случае оно печатается `CObject`.

`CDumpContext` Класс входит в состав отладочной и окончательной версии библиотеки, но `Dump` функция-член определяется только в отладочной версии. Используйте **#ifdef _DEBUG**  /  `#endif` инструкции для скобок диагностики кода, включая пользовательскую `Dump` функций-членов.

Прежде чем создавать собственный `CDumpContext` объекта, необходимо создать `CFile` объект, который служит в качестве назначения дампа.

Дополнительные сведения о `CDumpContext`, см. в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDumpContext`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cdumpcontext"></a>  CDumpContext::CDumpContext

Создает объект класса `CDumpContext`.

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на `CFile` объект, который является конечным дампа.

### <a name="remarks"></a>Примечания

`afxDump` Объект будет создан автоматически.

Не выполняйте запись в базовый `CFile` несмотря на то активна; в противном случае, контекст дампа будет мешать дампа. В среде Windows, выходные данные направляется к отладчику через функцию Windows `OutputDebugString`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

##  <a name="dumpashex"></a>  CDumpContext::DumpAsHex

Создает дамп указанного типа в формате шестнадцатеричных чисел.

```
CDumpContext& DumpAsHex(BYTE b);
CDumpContext& DumpAsHex(DWORD dw);
CDumpContext& DumpAsHex(int n);
CDumpContext& DumpAsHex(LONG l);
CDumpContext& DumpAsHex(LONGLONG n);
CDumpContext& DumpAsHex(UINT u);
CDumpContext& DumpAsHex(ULONGLONG n);
CDumpContext& DumpAsHex(WORD w);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `CDumpContext`.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член для помещения в дамп элемента указанного типа в шестнадцатеричном формате. Для помещения в дамп массив, вызовите [CDumpContext::HexDump](#hexdump).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

##  <a name="flush"></a>  CDumpContext::Flush

Заставляет все данные, оставшиеся в буферах, записываемых в файл, которые присоединяются к контексту дампа.

```
void Flush();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

##  <a name="getdepth"></a>  CDumpContext::GetDepth

Определяет, является ли глубоко или поверхностно дампа в процессе.

```
int GetDepth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Глубина дампа, задаваемое при помощи `SetDepth`.

### <a name="example"></a>Пример

  См. в примере [SetDepth](#setdepth).

##  <a name="hexdump"></a>  CDumpContext::HexDump

Выводит массив байтов, в формате шестнадцатеричных чисел.

```
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>Параметры

*lpszLine*<br/>
Строка для вывода в начале строки.

*pby*<br/>
Указатель на буфер, содержащий в байтах.

*nBytes*<br/>
Число байтов для помещения в дамп.

*nWidth*<br/>
Максимальное число байтов, записаны в строке (не ширину строки вывода).

### <a name="remarks"></a>Примечания

Для помещения в дамп типом один, конкретный элемент в шестнадцатеричном формате, вызовите [CDumpContext::DumpAsHex](#dumpashex).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

##  <a name="operator_lt_lt"></a>  CDumpContext::operator &lt;&lt;

Выводит указанные данные в контекст дампа.

```
CDumpContext& operator<<(const CObject* pOb);
CDumpContext& operator<<(const CObject& ob);
CDumpContext& operator<<(LPCTSTR lpsz);
CDumpContext& operator<<(const void* lp);
CDumpContext& operator<<(BYTE by);
CDumpContext& operator<<(WORD w);
CDumpContext& operator<<(DWORD dw);
CDumpContext& operator<<(int n);
CDumpContext& operator<<(double d);
CDumpContext& operator<<(float f);
CDumpContext& operator<<(LONG l);
CDumpContext& operator<<(UINT u);
CDumpContext& operator<<(LPCWSTR lpsz);
CDumpContext& operator<<(LPCSTR lpsz);
CDumpContext& operator<<(LONGLONG n);
CDumpContext& operator<<(ULONGLONG n);
CDumpContext& operator<<(HWND h);
CDumpContext& operator<<(HDC h);
CDumpContext& operator<<(HMENU h);
CDumpContext& operator<<(HACCEL h);
CDumpContext& operator<<(HFONT h);
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CDumpContext` ссылки. Использование возвращаемого значения, можно написать несколько операций вставки в одной строке исходного кода.

### <a name="remarks"></a>Примечания

Для перегруженного оператора вставки `CObject` указатели также, как и для большинство примитивных типов. Указатель на символ приводит к дамп содержимого строки; указатель на **void** приводит шестнадцатеричный дамп только адрес. Longlong приведенным к ПУСТОМУ приводит дамп 64-разрядного знакового целого числа; Значение ULONGLONG приводит дамп 64-разрядное целое число без знака.

Если вы используете IMPLEMENT_DYNAMIC или IMPLEMENT_SERIAL макрос в реализации класса, а затем оператор вставки через `CObject::Dump`, выводит имя вашей `CObject`-производного класса. В противном случае оно печатается `CObject`. При переопределении `Dump` функции класса, то можно предоставить более понятные выходные данные объекта содержимого вместо шестнадцатеричный дамп.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

##  <a name="setdepth"></a>  CDumpContext::SetDepth

Задает глубину для дампа.

```
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>Параметры

*nNewDepth*<br/>
Новое значение глубины.

### <a name="remarks"></a>Примечания

Если формирование дампа тип-примитив или простой `CObject` , не содержит указателей на другие объекты, то достаточно значение 0. Значение больше 0 задает глубокого дампа, когда все объекты были записаны рекурсивно. Например глубокое дамп коллекции выгружать все элементы коллекции. Вы можете использовать другие значения определенной глубины в производных классах.

> [!NOTE]
>  Циклические ссылки не обнаруживаются в глубокого дампы и может привести к бесконечных циклов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
