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
ms.openlocfilehash: e89bbc5f263dc9303140e43914619090109b8315
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753207"
---
# <a name="cdumpcontext-class"></a>Класс CDumpContext

Поддерживает ориентированных на поток диагностические данные в форме человекочитаемого текста.

## <a name="syntax"></a>Синтаксис

```
class CDumpContext
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDumpКонтекст::CDumpContext](#cdumpcontext)|Формирует объект `CDumpContext`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDumpContext::DumpAsHex](#dumpashex)|Сбрасывает указанный товар в гексадецимальном формате.|
|[CDumpКонтекст::Флеш](#flush)|Сбрасывает любые данные в буфер контексте дампа.|
|[CDumpКонтекст::GetDepth](#getdepth)|Получает несколько, соответствующие глубине свалки.|
|[CDumpКонтекст::HexDump](#hexdump)|Свалы байты, содержащиеся в массиве в гексадецимальном формате.|
|[CDumpКонтекст::SetDepth](#setdepth)|Устанавливает глубину свалки.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CDumpContext::оператор&lt;&lt;](#operator_lt_lt)|Вставляет переменные и объекты в контекст свалки.|

## <a name="remarks"></a>Remarks

`CDumpContext`не имеет базового класса.

Вы можете использовать [afxDump](diagnostic-services.md#afxdump) `CDumpContext` , заранее объявленный объект, для большинства ваших захоронений. Объект `afxDump` доступен только в версии Debug библиотеки класса Microsoft Foundation.

Некоторые из [служб диагностики](../../mfc/reference/diagnostic-services.md) памяти используют `afxDump` для их вывода.

В среде Windows выход из `afxDump` предопределенного объекта, `cerr` концептуально похожий на поток, `OutputDebugString`направляется в отладчик через функцию Windows.

Класс `CDumpContext` имеет перегруженную вставку () **<<** оператора `CObject` для указателей, который сбрасывает данные объекта. Если вам нужен пользовательский формат дампа для производного объекта, переудочните [CObject::Dump.](../../mfc/reference/cobject-class.md#dump) Большинство классов Фонда Майкрософт `Dump` реализуют переопределенную функцию члена.

Классы, которые не `CObject`являются `CString`производными от , таких как `CTime`, , `CTimeSpan`и , имеют свои собственные перегруженные `CDumpContext` операторы вставки, как это часто используются структуры, такие как `CFileStatus`, `CPoint`и `CRect`.

Если вы используете [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) или [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос `CObject::Dump` в реализации вашего класса, то распечатайте имя вашего `CObject`класса, полученного. В противном `CObject`случае, он будет печатать .

Класс `CDumpContext` доступен как с версиями библиотеки Отображения, так и с выпуском, но функция `Dump` участника определяется только в версии Debug. Используйте **#ifdef _DEBUG**  /  `#endif` заявления для скобки `Dump` вашего диагностического кода, включая пользовательские функции члена.

Прежде чем создать `CDumpContext` свой собственный `CFile` объект, необходимо создать объект, который служит местом захоронения.

Для получения `CDumpContext`дополнительной информации о , см. [Debugging MFC Applications](/visualstudio/debugger/mfc-debugging-techniques)

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDumpContext`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>CDumpКонтекст::CDumpContext

Строит объект класса. `CDumpContext`

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на `CFile` объект, который является местом захоронения.

### <a name="remarks"></a>Remarks

Объект `afxDump` строится автоматически.

Не пишите в основной контекст, `CFile` пока контекст дампа активен; в противном случае, вы будете вмешиваться в свалку. В среде Windows вывод направляется в отладчик через `OutputDebugString`функцию Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a>CDumpContext::DumpAsHex

Сбрасывает указанный тип, отформатированный как гексадецимальные числа.

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

### <a name="remarks"></a>Remarks

Вызовите эту функцию участника, чтобы сбросить элемент указанного типа как гексадецмальный номер. Чтобы сбросить массив, позвоните [CDumpContext::HexDump](#hexdump).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a>CDumpКонтекст::Флеш

Принуждает любые данные, оставшиеся в буферах, к файлу, прикрепленному к контексту свалки.

```cpp
void Flush();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a>CDumpКонтекст::GetDepth

Определяет, находится ли в процессе глубокая или неглубокая свалка.

```
int GetDepth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Глубина свалки, установленная `SetDepth`.

### <a name="example"></a>Пример

  Смотрите пример [SetDepth](#setdepth).

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a>CDumpКонтекст::HexDump

Сбрасывает массив байтов, отформатированных как гексадецимальные числа.

```cpp
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>Параметры

*lpszLine*<br/>
Строка к выходу в начале новой строки.

*пби*<br/>
Указатель на буфер, содержащий байты для сброса.

*nБайт*<br/>
Количество байтов для сброса.

*nWidth*<br/>
Максимальное количество байтов, сбрасываемых на линию (не ширина линии вывода).

### <a name="remarks"></a>Remarks

Чтобы сбросить один, определенный тип элемента в качестве гексадецимального номера, позвоните [cDumpContext::DumpAsHex](#dumpashex).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>CDumpContext::оператор&lt;&lt;

Выводы указанных данных в контекст свалки.

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

Ссылка `CDumpContext`. Используя значение возврата, можно написать несколько вставок на одной строке исходного кода.

### <a name="remarks"></a>Remarks

Оператор вставки перегружен как `CObject` для указателей, так и для большинства примитивных типов. Указатель на символ приводит к дампу содержимого строки; указатель **на аннулирование** приводит к гексадецимальной свалке адреса только. LONGLONG приводит к свалке 64-битного подписанного целых числа; ULONGLONG приводит к свалке 64-битного неподписанного бессетрика.

Если вы используете IMPLEMENT_DYNAMIC или IMPLEMENT_SERIAL макрос в реализации вашего `CObject::Dump`класса, то оператор `CObject`вставки, через , будет печатать имя вашего -производного класса. В противном `CObject`случае, он будет печатать . Если вы переопределяете `Dump` функцию класса, то можно обеспечить более значимый вывод содержимого объекта вместо гексадецимальной свалки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a>CDumpКонтекст::SetDepth

Устанавливает глубину свалки.

```cpp
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>Параметры

*nNewDepth*<br/>
Новое значение глубины.

### <a name="remarks"></a>Remarks

Если вы сбрасываете примитивный тип или простой, `CObject` который не содержит указателей на другие объекты, то достаточно значения 0. Значение, превышающее 0, определяет глубокую свалку, где все объекты сбрасываются рекурсивно. Например, глубокая свалка коллекции будет сбрасывать все элементы коллекции. Вы можете использовать другие определенные значения глубины в своих классах.

> [!NOTE]
> Круговые ссылки не обнаруживаются в глубоких сбросах и могут привести к бесконечным циклам.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
