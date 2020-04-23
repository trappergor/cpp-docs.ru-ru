---
title: Диагностические службы
ms.date: 11/04/2016
helpviewer_keywords:
- diagnosi [MFC]s, diagnostic services
- diagnostic macros [MFC], list of general MFC
- services [MFC], diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables [MFC]
- diagnostics [MFC], diagnostic functions and variables
- diagnostics [MFC], list of general MFC
- diagnosis [MFC], diagnostic functions and variables
- diagnosis [MFC], list of general MFC
- general diagnostic macros in MFC
- diagnostic macros [MFC]
- diagnostic services [MFC]
- object diagnostic functions in MFC
- diagnostics [MFC], diagnostic services
- diagnostic functions and variables [MFC]
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
ms.openlocfilehash: f952044f4320aea1a757559b3c9c51e8ffb7c3a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751653"
---
# <a name="diagnostic-services"></a>Диагностические службы

Библиотека Microsoft Foundation Class предоставляет множество служб диагностики, которые упрощают отладку программ. Эти службы включают в себя макросы и глобальные функции, позволяющие отслеживать выделение памяти для программы, записывать дамп содержимого объектов во время выполнения и печатать сообщения отладки во время выполнения. Макросы и глобальные функции диагностических служб сгруппированы в следующие категории:

- общие диагностические макросы;

- общие диагностические функции и переменные;

- функции диагностики объектов.

Эти макросы и функции доступны для всех классов, производных от `CObject` , в отладочной и окончательной версиях MFC. Тем не менее, все, кроме DEBUG_NEW и VERIFY ничего не делать в версии релиза.

В отладочной библиотеке все блоки выделенной памяти заключаются в последовательности "защитных байтов". Если эти байты изменяются в результате ошибочной операции записи в память, диагностические подпрограммы могут сообщить о проблеме. Если включить строку:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

в файле реализации все вызовы к **новому** будут хранить имя файла и номер строки, где произошло распределение памяти. Функция [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) будет отображать эту дополнительную информацию, что позволяет идентифицировать утечки памяти. Обратитесь также к классу [CDumpContext](../../mfc/reference/cdumpcontext-class.md) для получения дополнительной информации о диагностической продукции.

Кроме того, библиотека времени выполнения C также поддерживает ряд диагностических функций, которые можно использовать для отладки приложений. Для получения дополнительной информации смотрите [справку о времени работы](../../c-runtime-library/debug-routines.md) в справочнике по библиотеке Run-Time.

### <a name="mfc-general-diagnostic-macros"></a>Общие диагностические макросы MFC

|||
|-|-|
|[Утверждать](#assert)|Выводит сообщение и прерывает выполнение программы, если указанное выражение равно FALSE в отладочной версии библиотеки.|
|[ASSERT_KINDOF](#assert_kindof)|Проверяет, является ли объект объектом указанного класса или класса, производного от указанного.|
|[ASSERT_VALID](#assert_valid)|Проверяет внутреннюю допустимость объекта, вызывая его функцию-член `AssertValid` ; обычно переопределяется из `CObject`.|
|[DEBUG_NEW](#debug_new)|Предоставляет имя файла и номер строки для каждого выделения объекта в режиме отладки для выявления утечек памяти.|
|[DEBUG_ONLY](#debug_only)|Аналогично ASSERT, но не проверяет значение выражения; полезно для кода, который должен выполняться только в режиме отладки.|
|[ENSURE и ENSURE_VALID](#ensure)|Используйте для проверки правильности данных.|
|[THIS_FILE](#this_file)|Расширяется до имени файла, который компилируется.|
|[Трассировки](#trace)|Работает аналогично `printf`в отладочной версии библиотеки.|
|[Проверяем подлинность](#verify)|Аналогично ASSERT, но вычисляет выражение в окончательной версии библиотеки, а также в отладочной версии.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>Общие диагностические переменные и функции MFC

|||
|-|-|
|[afxDump](#afxdump)|Глобальная переменная, отправляя информацию [CDumpContext](../../mfc/reference/cdumpcontext-class.md) в окно вывода отладчика или в терминал отладки.|
|[afxMemDF](#afxmemdf)|Глобальная переменная, которая управляет поведением отладочного распределителя памяти.|
|[AfxCheckError](#afxcheckerror)|Глобальная переменная, используемая для проверки переданного значения SCODE на предмет того, представляет ли оно ошибку; если да, вызывается соответствующая ошибка.|
|[AfxCheckMemory](#afxcheckmemory)|Проверяет целостность всей выделенной на текущий момент памяти.|
|[Функция AfxDebugBreak](#afxdebugbreak)|Вызывает перерыв в исполнении.|
|[afxDump](#cdumpcontext_in_mfc)|При вызове в отладчике записывает дамп состояния объекта в процессе отладки.|
|[afxDump](#afxdump)|Внутренняя функция, которая сбрасывает состояние объекта во время отладки.|
|[AfxDumpStack](#afxdumpstack)|Создает образ текущего стека. Эта функция всегда компонуется статически.|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Включает дамп утечки памяти.|
|[AfxEnableMemoryTracking](#afxenablememorytracking)|Включает и отключает отслеживание памяти.|
|[AfxisMemoryBlock](#afxismemoryblock)|Проверяет, правильно ли выделен блок памяти.|
|[AfxisValidАдрес](#afxisvalidaddress)|Проверяет, находится ли диапазон адресов памяти в рамках области памяти программы.|
|[AfxIsValidString](#afxisvalidstring)|Определяет, является ли указатель на строку допустимым.|
|[AfxSetAllocHook](#afxsetallochook)|Обеспечивает вызов функции для каждого выделения памяти.|

### <a name="mfc-object-diagnostic-functions"></a>Функции диагностики объектов MFC

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|Выполняет указанную функцию для всех производных от `CObject`классов, которые поддерживают проверку типов во время выполнения.|
|[AfxdoForAllObjects](#afxdoforallobjects)|Выполняет указанную функцию для всех производных от `CObject`объектов, которые были выделены с помощью **new**.|

### <a name="mfc-compilation-macros"></a>MFC Компиляция Макрос

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Подавляет предупреждения компилятора об использовании унижаемых функций МФЦ.|

## <a name="_afx_secure_no_warnings"></a><a name="afx_secure_no_warnings"></a>_AFX_SECURE_NO_WARNINGS

Подавляет предупреждения компилятора об использовании унижаемых функций МФЦ.

### <a name="syntax"></a>Синтаксис

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>Пример

Этот образец кода вызовет предупреждение компилятора, если _AFX_SECURE_NO_WARNINGS не определены.

```cpp
// define this before including any afx files in *pch.h* (*stdafx.h* in Visual Studio 2017 and earlier)
#define _AFX_SECURE_NO_WARNINGS
```

```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a><a name="afxdebugbreak"></a>AfxDebugBreak

Вызов ими функции, чтобы вызвать перерыв `AfxDebugBreak`(в месте вызова) в выполнении версии отладки вашего приложения MFC.

### <a name="syntax"></a>Синтаксис

```cpp
void AfxDebugBreak( );
```

### <a name="remarks"></a>Remarks

`AfxDebugBreak`не влияет на выпуск версий приложения MFC и должен быть удален. Эта функция должна использоваться только в приложениях MFC. Используйте версию Win32 `DebugBreak`API, чтобы вызвать перерыв в приложениях, не входящих в MFC.

### <a name="requirements"></a>Требования

**Заголовок:** afxver_.h

## <a name="assert"></a><a name="assert"></a>Утверждать

Оценивает его аргумент.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>Параметры

*booleanВыражение*<br/>
Определяет выражение (включая значения указателя), которое оценивается до ненулевого или 0.

### <a name="remarks"></a>Remarks

Если результат 0, макрос печатает диагностическое сообщение и прерывает программу. Если условие ненулевое, оно ничего не делает.

Диагностическое сообщение имеет форму

`assertion failed in file <name> in line <num>`

где *имя* — это имя исходного файла, а *num* — это номер строки утверждения, скакавшего в исходном файле.

В версии релиза MFC ASSERT не оценивает выражение и, таким образом, не будет прерывать программу. Если выражение должно быть оценено независимо от окружающей среды, используйте макрос VERIFY вместо ASSERT.

> [!NOTE]
> Эта функция доступна только в версии Debug MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="assert_kindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF

Этот макрос утверждает, что объект, на который указывается, является объектом указанного класса или объектом класса, полученным из указанного класса.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, `CObject`полученного из полученных.

*побъект*<br/>
Указатель на объект класса.

### <a name="remarks"></a>Remarks

Параметр *побъекта* должен быть указателем на объект и может быть **конст.** Указывается объект, и класс `CObject` должен поддерживать информацию о классе времени выполнения. В качестве примера, `pDocument` чтобы убедиться, что `CMyDoc` это указатель на объект класса, или любой из его производных, можно кодировать:

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

Использование `ASSERT_KINDOF` макроса точно так же, как кодирование:

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

Эта функция работает только для классов, заявленных с «DECLARE_DYNAMIC» (запуск-объект-модель-услуги.md'declare_dynamic или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.

> [!NOTE]
> Эта функция доступна только в версии Debug MFC.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="assert_valid"></a><a name="assert_valid"></a>ASSERT_VALID

Используйте для проверки своих предположений о достоверности внутреннего состояния объекта.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>Параметры

*pObject*<br/>
Определяет объект класса, полученный из `CObject` того, который имеет передний вариант функции `AssertValid` члена.

### <a name="remarks"></a>Remarks

ASSERT_VALID называет `AssertValid` функцию члена объекта, пройдена, в качестве аргумента.

В версии выпуска MFC ASSERT_VALID ничего не делает. В версии Debug он проверяет указатель, проверяет сятворное `AssertValid` и вызывает собственные функции члена объекта. Если какой-либо из этих тестов не удается, сообщение оповещения отображается таким же образом, как [ASSERT](#assert).

> [!NOTE]
> Эта функция доступна только в версии Debug MFC.

Для получения дополнительной информации и примеров [см.](/visualstudio/debugger/mfc-debugging-techniques)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="debug_new"></a><a name="debug_new"></a>DEBUG_NEW

Помогает в поиске утечек памяти.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>Remarks

Вы можете использовать DEBUG_NEW везде в вашей программе, что вы обычно используете **новый** оператор для выделения кучи хранения.

В режиме отладки (когда определяется **символ _DEBUG)** DEBUG_NEW отслеживает имя файла и номер строки для каждого объекта, который он выделяет. Затем при использовании функции [CMemoryState::DumpAllObjectsSince,](cmemorystate-structure.md#dumpallobjectssince) каждый объект, выделенный с DEBUG_NEW отображается с именем файла и номером строки, где он был выделен.

Чтобы использовать DEBUG_NEW, вставьте следующую директиву в исходные файлы:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Как только вы введете эту директиву, препроцессор будет вставлять DEBUG_NEW везде, где вы используете **новые,** и MFC делает все остальное. Когда вы компилируете версию программы, DEBUG_NEW решает с **простой новой** операции, и информация об имени файла и номере строки не генерируется.

> [!NOTE]
> В предыдущих версиях MFC (4.1 и `#define` ранее) необходимо было разместить заявление после всех заявлений, которые назывались IMPLEMENT_DYNCREATE или IMPLEMENT_SERIAL макросов. Это больше не требуется.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="debug_only"></a><a name="debug_only"></a>DEBUG_ONLY

В режиме отладки (когда определяется **символ _DEBUG)** DEBUG_ONLY оценивает его аргумент.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>Remarks

В сборке релиза DEBUG_ONLY не оценивает свой аргумент. Это полезно, когда у вас есть код, который должен быть выполнен только в отладке сборки.

Макрос DEBUG_ONLY эквивалентен окружающему `#endif` *выражению* с `#ifdef _DEBUG` и .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

### <a name="ensure-and-ensure_valid"></a><a name="ensure"></a>ENSURE и ENSURE_VALID

Используйте для проверки правильности данных.

### <a name="syntax"></a>Синтаксис

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>Параметры

*booleanВыражение*<br/>
Определяет выражение булеана для проверки.

### <a name="remarks"></a>Remarks

Целью этих макросов является улучшение проверки параметров. Макросы предотвращают дальнейшую обработку неправильных параметров в коде. В отличие от макросов ASSERT, макросы ENSURE в дополнение к генерации утверждения делают исключение.

Макросы ведут себя двумя способами, в соответствии с конфигурацией проекта. Макросвызова вызывают ASSERT, а затем бросают исключение, если утверждение не удается. Таким образом, в конфигурациях Debug (т.е. в тех случаях, когда определяется _DEBUG) макросы производят утверждение и исключение, в то время как в конфигурациях Release макросы производят только исключение (ASSERT не оценивает выражение в конфигурациях Release).

МакроENSURE_ARG действует как макрос ENSURE.

ENSURE_VALID вызывает ASSERT_VALID макрос (который имеет эффект только в сборках Debug). Кроме того, ENSURE_VALID бросает исключение, если указатель NULL. Тест NULL выполняется как в конфигурациях Debug, так и в выпусках.

Если какой-либо из этих тестов не удается, сообщение оповещения отображается таким же образом, как ASSERT. Макрос при необходимости выбрасывает недействительное исключение аргумента.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="this_file"></a><a name="this_file"></a>THIS_FILE

Расширяется до имени файла, который компилируется.

### <a name="syntax"></a>Синтаксис

```
THIS_FILE
```

### <a name="remarks"></a>Remarks

Информация используется макросами ASSERT и VERIFY. Мастер приложений и мастера кода размещают макрос в создаваемых ими файлах исходного кода.

### <a name="example"></a>Пример

```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the
// compiler recognizes.
```

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="trace"></a><a name="trace"></a>Трассировки

Отправляет указанную строку отладчику текущего приложения.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>Remarks

[См. ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) для описания TRACE. TRACE и ATLTRACE2 ведут одинаковое поведение.

В версии отладки MFC этот макрос отправляет указанную строку отладчику текущего приложения. В сборке релиза этот макрос компилируется ни к чему (код не генерируется вообще).

Для получения дополнительной [информации](/visualstudio/debugger/mfc-debugging-techniques)см.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="verify"></a><a name="verify"></a>Проверяем подлинность

В версии Debug МФЦ оценивает сяобнистые.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>Параметры

*booleanВыражение*<br/>
Определяет выражение (включая значения указателя), которое оценивается до ненулевого или 0.

### <a name="remarks"></a>Remarks

Если результат 0, макрос печатает диагностическое сообщение и останавливает программу. Если условие ненулевое, оно ничего не делает.

Диагностическое сообщение имеет форму

`assertion failed in file <name> in line <num>`

где *имя* — это имя исходного файла, а *num* — это номер строки утверждения, скакавшего в исходном файле.

В версии релиза MFC VERIFY оценивает выражение, но не печатает и не прерывает программу. Например, если выражение является вызовом функции, вызов будет сделан.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc"></a>afxDump (CDumpContext в MFC)

Обеспечивает основные возможности сброса объектов в приложении.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>Remarks

`afxDump`является предопределенным объектом [CDumpContext,](../../mfc/reference/cdumpcontext-class.md) `CDumpContext` который позволяет отправлять информацию в окно вывода отладчика или в терминал отладки. Как правило, `afxDump` вы поставляете в качестве `CObject::Dump`параметра.

В соответствии с Windows `afxDump` NT и всеми версиями Windows, выход отправляется в окно вывода-отладки Visual C, когда вы отлажаете приложение.

Эта переменная определяется только в версии Debug MFC. Для получения `afxDump`дополнительной информации о , см. [Debugging MFC Applications](/visualstudio/debugger/mfc-debugging-techniques)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxdump-internal"></a><a name="afxdump"></a>AfxDump (внутренний)

Внутренняя функция, которую MFC использует для сброса состояния объекта во время отладки.

### <a name="syntax"></a>Синтаксис

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Параметры

*Тн*<br/>
Указатель на объект класса, полученный `CObject`из .

### <a name="remarks"></a>Remarks

`AfxDump`вызывает функцию `Dump` члена объекта и отправляет информацию в `afxDump` место, указанное переменной. `AfxDump`доступен только в версии Debug MFC.

Ваш программный код `AfxDump`не должен вызываться, а вместо этого вызывать функцию `Dump` участника соответствующего объекта.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxmemdf"></a><a name="afxmemdf"></a>afxMemDF

Эта переменная доступна от отладчика или вашей программы и позволяет настроить диагностику распределения.

```
int  afxMemDF;
```

### <a name="remarks"></a>Remarks

`afxMemDF`может иметь следующие значения, указанные в `afxMemDF`перечислении:

- `allocMemDF`Включает отладку разлесть (настройка по умолчанию в библиотеке Debug).

- `delayFreeMemDF`Задержки с освобождением памяти. В то время как ваша программа освобождает блок памяти, allocator не возвращает эту память в базовую операционную систему. Это создадит максимальную нагрузку памяти на вашу программу.

- `checkAlwaysMemDF`Вызовы `AfxCheckMemory` каждый раз, когда память выделяется или освобождается. Это значительно замедлит распределение памяти и дислокации.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheckError

Эта функция проверяет пройденое SCODE, чтобы увидеть, является ли это ошибкой.

```cpp
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>Remarks

Если это ошибка, функция бросает исключение. Если пройденный SCODE E_OUTOFMEMORY, функция бросает [CMemoryException,](../../mfc/reference/cmemoryexception-class.md) позвонив [в AfxThrowMemory.](exception-processing.md#afxthrowmemoryexception) В противном случае функция бросает [COleException,](../../mfc/reference/coleexception-class.md) позвонив [afxThrowOleException](exception-processing.md#afxthrowoleexception).

Эта функция может быть использована для проверки значений возврата вызовов к функциям OLE в приложении. Проверяя значение возврата с помощью этой функции в приложении, вы можете правильно реагировать на условия ошибки с минимальным количеством кода.

> [!NOTE]
> Эта функция имеет тот же эффект в отладке и неотладя сборки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxcheckmemory"></a><a name="afxcheckmemory"></a>AfxCheckMemory

Эта функция проверяет свободный пул памяти и при необходимости печатает сообщения об ошибках.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если нет ошибок памяти; в противном случае 0.

### <a name="remarks"></a>Remarks

Если функция не обнаруживает повреждения памяти, она ничего не печатает.

Проверяются все блоки памяти, в настоящее время выделенные на куче, включая блоки, выделенные **новыми,** но не выделенными прямыми вызовами для основных распределителей памяти, такими как функция **malloc** или функция `GlobalAlloc` Windows. Если какой-либо блок будет признан поврежденным, сообщение печатается на выходе отладчика.

Если вы включаете строку

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

в модуле программы, `AfxCheckMemory` затем последующие вызовы, чтобы показать имя файла и номер строки, где была выделена память.

> [!NOTE]
> Если модуль содержит одну или несколько реализаций сериализируемых `#define` классов, то вы должны поставить строку после последнего IMPLEMENT_SERIAL макровызова.

Эта функция работает только в версии Debug MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxdump-mfc"></a><a name="afxdump"></a>AfxDump (MFC)

Вызов этой функции в то время как в отладчике сбросить состояние объекта во время отладки.

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Параметры

*Тн*<br/>
Указатель на объект класса, полученный `CObject`из .

### <a name="remarks"></a>Remarks

`AfxDump`вызывает функцию `Dump` члена объекта и отправляет информацию в `afxDump` место, указанное переменной. `AfxDump`доступен только в версии Debug MFC.

Ваш программный код `AfxDump`не должен вызываться, а вместо этого вызывать функцию `Dump` участника соответствующего объекта.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxdumpstack"></a><a name="afxdumpstack"></a>AfxDumpStack

Эта глобальная функция может быть использована для создания изображения текущего стека.

```cpp
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>Параметры

*dwTarget*<br/>
Указывает цель выхода свалки. Возможные значения, которые могут быть объединены с помощью оператора bitwise-OR **(&#124;), **следующие:

- AFX_STACK_DUMP_TARGET_TRACE отправляет выход с помощью макроса [TRACE.](#trace) Макрос TRACE генерирует выход только в отладке; он не генерирует выход в сборках выпуска. Кроме того, TRACE может быть перенаправлен на другие цели, кроме отладчика.

- AFX_STACK_DUMP_TARGET_DEFAULT отправляет выход свалки в цель по умолчанию. Для сборки отладки выход переходит к макросу TRACE. При сборке релиза выход переходит в Clipboard.

- AFX_STACK_DUMP_TARGET_CLIPBOARD отправляет выход только на Clipboard. Данные размещаются на Clipboard в виде обычного текста с использованием формата CF_TEXT Clipboard.

- AFX_STACK_DUMP_TARGET_BOTH отправляет выход на Clipboard и на макрос TRACE одновременно.

- AFX_STACK_DUMP_TARGET_ODS отправляет выход непосредственно отладчику с помощью `OutputDebugString()`функции Win32. Эта опция будет генерировать выход отладки как в отладке, так и в сборках релизов при подключении отладчика к процессу. AFX_STACK_DUMP_TARGET_ODS всегда достигает отладчика (если он подключен) и не может быть перенаправлен.

### <a name="remarks"></a>Remarks

Приведенный ниже пример отражает одну строку `AfxDumpStack` вывода, генерируемого из вызова от обработчика кнопок в диалоговом приложении MFC:

```Output
=== begin AfxDumpStack output ===
00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes
0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes
0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,
unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct
AFX_CMDHANDLE
0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes
00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes
00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned
int,long) + 312 bytes
00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned
int,unsigned int,long,long *) + 83 bytes
00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned
int,unsigned int,long) + 46 bytes
004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct
HWND__ *,unsigned int,unsigned int,long) + 237 bytes
00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned
int,unsigned int,long) + 129 bytes
BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes
BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes
=== end AfxDumpStack() output ===
```

Каждая строка в вышеуказанном выводе указывает адрес последнего вызова функции, полное имя пути модуля, содержащего вызов функции, и вызванный прототип функции. Если вызов функции на стеке не происходит по точному адресу функции, отображается смещение байтов.

Например, в следующей таблице описывается первая строка вышеуказанного вывода:

|Выходные данные|Описание|
|------------|-----------------|
|`00427D55:`|Обратный адрес последнего вызова функции.|
|`DUMP2\DEBUG\DUMP2.EXE!`|Полное имя пути модуля, содержащего вызов функции.|
|`void AfxDumpStack(unsigned long)`|Прототип функции называется.|
|`+ 181 bytes`|Смещение байтов от адреса прототипа функции `void AfxDumpStack(unsigned long)`(в данном случае) к `00427D55`обратному адресу (в данном случае).|

`AfxDumpStack`доступна в версиях отладки и недебага библиотек МФЦ; однако функция всегда связана статично, даже если ваш исполняемый файл использует MFC в общем DLL. В реализации общей библиотеки функция содержится в MFCS42. Библиотека LIB (и ее варианты).

Чтобы успешно использовать эту функцию:

- Файл IMAGEHLP. DLL должен быть на вашем пути. Если у вас нет этого DLL, функция будет отображать сообщение об ошибке. См [библиотека помощи изображений](/windows/win32/Debug/image-help-library) для получения информации о наборе функций, предоставляемых IMAGEHLP.

- Модули, которые имеют кадры в стеке, должны включать информацию об отладке. Если они не содержат информацию об отладке, функция по-прежнему будет генерировать след стека, но след будет менее подробным.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump

Позволяет и отклоняет свалку утечки памяти в AFX_DEBUG_STATE деструктора.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>Параметры

*bDump*<br/>
(в) TRUE указывает на то, что дамп утечки памяти включен; FALSE указывает на то, что свалка утечки памяти отключена.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение для этого флага.

### <a name="remarks"></a>Remarks

Когда приложение выгружает библиотеку MFC, она выполняет проверку на наличие утечек памяти. На данный момент, любые утечки памяти сообщаются пользователю через окно **debug** Visual Studio.

Если приложение загружает другую библиотеку перед библиотекой MFC, некоторые выделения памяти в этой библиотеке ошибочно выводятся как утечки памяти. Ложные утечки памяти могут привести к медленному закрытию приложения, пока библиотека MFC сообщает о них. В этом случае воспользуйтесь `AfxEnableMemoryLeakDump` , чтобы отключить дамп утечки памяти.

> [!NOTE]
> При использовании этого метода для отключения дампа утечки памяти вы не будете получать отчеты о действительных утечках памяти в приложении. Этот метод следует использовать только в том случае, если вы уверены, что в отчете представлены только ложные утечки памяти.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnableMemoryTracking

Диагностическое отслеживание памяти обычно включено в версии Debug MFC.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>Параметры

*bTrack*<br/>
Установка этого значения для TRUE включает отслеживание памяти; FALSE выключает его.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая настройка флага слежения.

### <a name="remarks"></a>Remarks

Используйте эту функцию, чтобы отключить отслеживание на разделах кода, которые, как вы знаете, правильно распределяют блоки.

Для получения `AfxEnableMemoryTracking`дополнительной информации о , см. [Debugging MFC Applications](/visualstudio/debugger/mfc-debugging-techniques)

> [!NOTE]
> Эта функция работает только в версии Debug MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxismemoryblock"></a><a name="afxismemoryblock"></a>AfxisMemoryBlock

Тестирует адрес памяти, чтобы убедиться, что он представляет собой в настоящее время активный блок памяти, который был выделен диагностической версией **нового.**

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указывает на блок памяти для тестирования.

*nБайт*<br/>
Содержит длину блока памяти в байтах.

*plRequestНомер*<br/>
Указывает на **длинную** целых ряд, которая будет заполнена номером последовательности распределения блока памяти, или ноль, если он не представляет собой действующий блок памяти.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если блок памяти в настоящее время выделен и длина правильная; в противном случае 0.

### <a name="remarks"></a>Remarks

Он также проверяет указанный размер по сравнению с первоначальным выделенным размером. Если функция возвращается ненулевой, номер последовательности распределения возвращается в *plRequestNumber*. Это число представляет порядок, в котором блок был выделен по отношению ко всем другим **новым** выделениям.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxisvalidaddress"></a><a name="afxisvalidaddress"></a>AfxisValidАдрес

Тесты любого адреса памяти, чтобы убедиться, что он полностью содержится в пространстве памяти программы.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>Параметры

*Lp*<br/>
Указывает на адрес памяти для тестирования.

*nБайт*<br/>
Содержит количество байтов памяти, которые должны быть проверены.

*bReadWrite*<br/>
Определяет, является ли память как для чтения и письма (TRUE) или просто чтение (FALSE).

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках, ненулевой, если указанный блок памяти полностью содержится в пространстве памяти программы; в противном случае 0.

В неотлипового построения, незеро, если *lp* не является NULL; в противном случае 0.

### <a name="remarks"></a>Remarks

Адрес не ограничивается блоками, выделенными **новым**.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxisvalidstring"></a><a name="afxisvalidstring"></a>AfxisValidString

Используйте эту функцию, чтобы определить, является ли указке строки действительным.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
Указатель для тестирования.

*nДлина*<br/>
Определяет длину строки, которая будет проверена, в байтах. Значение -1 указывает на то, что строка будет нулевым.

### <a name="return-value"></a>Возвращаемое значение

В отладке сборки, ненулевой, если указанный указатель указывает на строку указанного размера; в противном случае 0.

В неотлипового построения, ненулевой, если *lpsz* не является NULL; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxsetallochook"></a><a name="afxsetallochook"></a>AfxSetAllocHook

Устанавливает сяк, позволяющий вызывать заданную функцию перед выделением каждого блока памяти.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>Параметры

*pfnAllocHook*<br/>
Упогоняет название функции вызова. Смотрите Замечания для прототипа функции распределения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вы хотите разрешить распределение; в противном случае 0.

### <a name="remarks"></a>Remarks

Отлаженный отлаженный памяти Microsoft Foundation Library может вызвать функцию крючка, определяемого пользователем, чтобы пользователь мог контролировать распределение памяти и контролировать, разрешено ли выделение. Функции крюк распределения прототипируются следующим образом:

**BOOL AFXAPI AllocHook (size_t** `nSize` **, BOOL** `bObject`, **LONG);** **, LONG** `lRequestNumber`

*Nsize*<br/>
Размер предлагаемого распределения памяти.

*bObject*<br/>
TRUE, если выделение предназначено для объекта, полученного; `CObject` в противном случае FALSE.

*lRequestНомер*<br/>
Номер последовательности распределения памяти.

Обратите внимание, что конвенция вызова AFXAPI подразумевает, что вызывающая часть должна удалить параметры из стека.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxdoForAllClasses

Вызывает указанную функцию итерации `CObject`для всех серийных классов в пространстве памяти приложения.

```cpp
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Параметры

*Pfn*<br/>
Указывает на функцию итерации, которая будет вызвана для каждого класса. Аргументы функции являются указателем `CRuntimeClass` на объект и недействительным указателем на дополнительные данные, которые абонент поставляет в функцию.

*pContext*<br/>
Указывает на дополнительные данные, которые абонент может предоставить функции итерации. Этот указатель может быть NULL.

### <a name="remarks"></a>Remarks

`CObject`Серийные классы являются классами, полученными с использованием макроса DECLARE_SERIAL. Указатель, передаваемый `AfxDoForAllClasses` в *pContext,* передается указанной функции итерации каждый раз, когда он вызывается.

> [!NOTE]
> Эта функция работает только в версии Debug MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="afxdoforallobjects"></a><a name="afxdoforallobjects"></a>AfxdoForAllObjects

Выполняет указанную функцию итерации для `CObject` всех объектов, полученных из выделенных с **новым.**

```cpp
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Параметры

*Pfn*<br/>
Указывает на функцию итерации для выполнения для каждого объекта. Аргументы функции являются указателем `CObject` на и недействительным указателем на дополнительные данные, которые абонент поставляет в функцию.

*pContext*<br/>
Указывает на дополнительные данные, которые абонент может предоставить функции итерации. Этот указатель может быть NULL.

### <a name="remarks"></a>Remarks

Стек, глобальные или встроенные объекты не перечисляются. Указатель, передаваемый `AfxDoForAllObjects` в *pContext,* передается указанной функции итерации каждый раз, когда он вызывается.

> [!NOTE]
> Эта функция работает только в версии Debug MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Кобъект::D](cobject-class.md#dump)
