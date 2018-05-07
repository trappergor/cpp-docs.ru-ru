---
title: Диагностические службы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2332090032a93152b6c841336538bf9d45984300
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="diagnostic-services"></a>Диагностические службы
Библиотека Microsoft Foundation Class предоставляет множество служб диагностики, которые упрощают отладку программ. Эти службы включают в себя макросы и глобальные функции, позволяющие отслеживать выделение памяти для программы, записывать дамп содержимого объектов во время выполнения и печатать сообщения отладки во время выполнения. Макросы и глобальные функции диагностических служб сгруппированы в следующие категории:  
  
-   общие диагностические макросы;  
  
-   общие диагностические функции и переменные;  
  
-   функции диагностики объектов.  
  
 Эти макросы и функции доступны для всех классов, производных от `CObject` , в отладочной и окончательной версиях MFC. Однако все они, за исключением `DEBUG_NEW` и **VERIFY** , в окончательной версии не работают.  
  
 В отладочной библиотеке все блоки выделенной памяти заключаются в последовательности "защитных байтов". Если эти байты изменяются в результате ошибочной операции записи в память, диагностические подпрограммы могут сообщить о проблеме. Если включить строку:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 в файл реализации, все вызовы **new** будут сохранять имя файла и номер строки, в которой выполняется выделение памяти. Функция [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) будет выводить дополнительную информацию, позволяющую выявить утечки памяти. Дополнительные сведения о выходных диагностических данных см. также в описании класса [CDumpContext](../../mfc/reference/cdumpcontext-class.md) .  
  
 Кроме того, библиотека времени выполнения C также поддерживает ряд диагностических функций, которые можно использовать для отладки приложений. Дополнительные сведения см. в разделе [Подпрограммы отладки](../../c-runtime-library/debug-routines.md) справочника по библиотеке времени выполнения.  
  
### <a name="mfc-general-diagnostic-macros"></a>Общие диагностические макросы MFC  
  
|||  
|-|-|  
|[ASSERT](#assert)|Выводит сообщение и прерывает выполнение программы, если указанное выражение равно **FALSE** в отладочной версии библиотеки.|  
|[ASSERT_KINDOF](#assert_kindof)|Проверяет, является ли объект объектом указанного класса или класса, производного от указанного.|  
|[ASSERT_VALID](#assert_valid)|Проверяет внутреннюю допустимость объекта, вызывая его функцию-член `AssertValid` ; обычно переопределяется из `CObject`.|
|[DEBUG_NEW](#debug_new)|Предоставляет имя файла и номер строки для каждого выделения объекта в режиме отладки для выявления утечек памяти.|  
|[DEBUG_ONLY](#debug_only)|Аналогично **ASSERT** , но не проверяет значение выражения; полезно для кода, который должен выполняться только в режиме отладки.|  
|[УБЕДИТЕСЬ, что и ENSURE_VALID](#ensure)|Используйте для проверки правильности данных.|
|[THIS_FILE](#this_file)|Имя файла, скомпилированного при развертывании.|
|[TRACE](#trace)|Работает аналогично `printf`в отладочной версии библиотеки.|  
|[VERIFY](#verify)|Аналогично **ASSERT** , но вычисляет выражение в окончательной версии библиотеки, а также в отладочной версии.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>Общие диагностические переменные и функции MFC  
  
|||  
|-|-|  
|[afxDump](#afxdump)|Глобальная переменная, которая отправляет информацию [CDumpContext](../../mfc/reference/cdumpcontext-class.md) в окно выходных данных отладчика или в терминал отладки.|  
|[afxMemDF](#afxmemdf)|Глобальная переменная, которая управляет поведением отладочного распределителя памяти.|  
|[AfxCheckError](#afxcheckerror)|Глобальная переменная, используемая для проверки переданного значения **SCODE** на предмет того, представляет ли оно ошибку; если да, вызывается соответствующая ошибка.|  
|[AfxCheckMemory](#afxcheckmemory)|Проверяет целостность всей выделенной на текущий момент памяти.|  
|[Функция AfxDebugBreak](#afxdebugbreak)|Приводит к разрыву выполнения.|
|[AfxDump](#cdumpcontext_in_mfc)|При вызове в отладчике записывает дамп состояния объекта в процессе отладки.|  
|[AfxDump](#afxdump)|Внутренняя функция, которая выводит состояние объекта во время отладки.|
|[AfxDumpStack](#afxdumpstack)|Создает образ текущего стека. Эта функция всегда компонуется статически.|  
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Включает дамп утечки памяти.|  
|[AfxEnableMemoryTracking](#afxenablememorytracking)|Включает и отключает отслеживание памяти.|  
|[AfxIsMemoryBlock](#afxismemoryblock)|Проверяет, правильно ли выделен блок памяти.|  
|[AfxIsValidAddress](#afxisvalidaddress)|Проверяет, находится ли диапазон адресов памяти в рамках области памяти программы.|  
|[AfxIsValidString](#afxisvalidstring)|Определяет, является ли указатель на строку допустимым.|  
|[AfxSetAllocHook](#afxsetallochook)|Обеспечивает вызов функции для каждого выделения памяти.|  
  
### <a name="mfc-object-diagnostic-functions"></a>Функции диагностики объектов MFC  
  
|||  
|-|-|  
|[AfxDoForAllClasses](#afxdoforallclasses)|Выполняет указанную функцию для всех производных от `CObject`классов, которые поддерживают проверку типов во время выполнения.|  
|[AfxDoForAllObjects](#afxdoforallobjects)|Выполняет указанную функцию для всех производных от `CObject`объектов, которые были выделены с помощью **new**.|  

### <a name="mfc-compilation-macros"></a>Компиляция макросов MFC
|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Подавляет предупреждения компилятора для использования устаревших функций MFC.|  


## <a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS
Подавляет предупреждения компилятора для использования устаревших функций MFC.  
   
### <a name="syntax"></a>Синтаксис   
```  
_AFX_SECURE_NO_WARNINGS  
```     
### <a name="example"></a>Пример  
 В этом примере кода вызовет предупреждение компилятора, если _AFX_SECURE_NO_WARNINGS не определены.  
  
 ```cpp
// define this before including any afx files in stdafx.h
#define _AFX_SECURE_NO_WARNINGS
```
```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a> Функция AfxDebugBreak
Эта функция вызывается для привести к сбою (в месте вызова `AfxDebugBreak`) в процессе выполнения отладочной версии приложения MFC.  

### <a name="syntax"></a>Синтаксис    
```
void AfxDebugBreak( );    
```  
   
### <a name="remarks"></a>Примечания  
 `AfxDebugBreak` не оказывает влияния в версии приложения MFC и должна быть удалена. Эта функция должна использоваться только в приложениях MFC. Используйте версию API-интерфейса Win32, **DebugBreak**, чтобы привести к сбою в приложениях, не являющихся MFC.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxver_.h   

##  <a name="assert"></a>  ASSERT
 Проверяет его аргумент.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Указывает выражение (включая значения указателя), результатом вычисления которого нуля или равен нулю.  
  
### <a name="remarks"></a>Примечания  
 Если результат равен 0, макрос выводит диагностическое сообщение и прерывает выполнение программы. Если условие имеет ненулевое значение, он не выполняет никаких действий.  
  
 Диагностическое сообщение имеет форму  
  
 `assertion failed in file <name> in line <num>`  
  
 где *имя* — имя исходного файла и *num* — это номер строки утверждения, завершившегося ошибкой в исходном файле.  
  
 В окончательной версии MFC **ASSERT** не вычисляет выражение и таким образом, не будут прерваны программы. Если выражение должно вычисляться независимо от среды, используйте **ПРОВЕРЬТЕ** макрос вместо **ASSERT**.  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="assert_kindof"></a>  ASSERT_KINDOF  
 Этот макрос подтверждает, что объект, на который указывает — это объект указанного класса или объекта класса, который является производным от указанного класса.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>Параметры  
 *classname*  
 Имя `CObject`-производного класса.  
  
 *pObject*  
 Указатель на объект класса.  
  
### <a name="remarks"></a>Примечания  
 *Pobject* параметр должен быть указателем на объект и может быть **const**. Указывает объект, а класс должен поддерживать `CObject` сведения о классе во время выполнения. Например, чтобы убедиться, что `pDocument` является указателем на объект `CMyDoc` класса или любого из его производных кода:  
  
 [!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 С помощью `ASSERT_KINDOF` макрос совпадает кодирования:  
  
 [!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 Эта функция работает только для классов, объявленные с [DECLARE_DYNAMIC] (#declare_dynamic выполнения время объект модели services.md или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="assert_valid"></a>  ASSERT_VALID  
 Используется для проверки своих предположений о допустимости внутреннего состояния объекта.  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указывает объект класса, производного от `CObject` с переопределение `AssertValid` функции-члена.  
  
### <a name="remarks"></a>Примечания  
 `ASSERT_VALID` вызовы `AssertValid` функции-члена объекта передана в качестве аргумента.  
  
 В окончательной версии MFC `ASSERT_VALID` не выполняет никаких действий. В отладочной версии, он проверяет указатель, проверяет **NULL**и вызывает метод объекта собственные `AssertValid` функции-члены. Если любой из этих тестов завершается с ошибкой, так же, как отображается предупреждающее сообщение [ASSERT](#assert).  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  
  
 Дополнительные сведения и примеры см. в разделе [отладки приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW  
 Помогает в поиске утечек памяти.  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `DEBUG_NEW` везде в программе, которые обычно используются **новый** оператор для выделения памяти в куче.  
  
 В режиме отладки (когда **_DEBUG** символ определен), `DEBUG_NEW` сохраняет отслеживания объекта файла и номер строки для каждого объекта, которому выделяется память. Затем, при использовании [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) каждый объект функции-члена, выделенных с помощью `DEBUG_NEW` указывается имя файла и номер строки, где было выполнено выделение.  
  
 Чтобы использовать `DEBUG_NEW`, вставьте следующую директиву в исходные файлы:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 После добавления этой директивы препроцессора вставит `DEBUG_NEW` везде, где используется **новый**, и MFC делает все остальное. При компиляции окончательной версии программы, `DEBUG_NEW` становится простой **новый** операции и имя файла и номере строки не создаются.  
  
> [!NOTE]
>  В предыдущих версиях MFC (4.1 и более ранних версий), необходимые для размещения `#define` инструкции после всех инструкций, которые вызваны `IMPLEMENT_DYNCREATE` или `IMPLEMENT_SERIAL` макросы. Это больше не требуется.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY  
 В режиме отладки (когда **_DEBUG** символ определен), `DEBUG_ONLY` проверяет его аргумент.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>Примечания  
 В сборке выпуска **DEBUG_ONLY** его аргумент не вычисляется. Это полезно в том случае, если у вас есть код, который должен быть выполнен только в отладочных построениях.  
  
 `DEBUG_ONLY` Макрос эквивалентен вокруг *выражение* с **#ifdef _DEBUG** и `#endif`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

 ### <a name="ensure"></a>  УБЕДИТЕСЬ, что и ENSURE_VALID
Используйте для проверки правильности данных.  
   
### <a name="syntax"></a>Синтаксис    
```
ENSURE(  booleanExpression )  
ENSURE_VALID( booleanExpression  )  
```
### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Указывает логическое выражение, которое необходимо проверить.  
   
### <a name="remarks"></a>Примечания  
 Эти макросы предназначена для повышения проверки параметров. Макросы препятствуют дальнейшей обработке неверные параметры в коде. В отличие от **ASSERT** макросы, **УБЕДИТЕСЬ, что** макросы создаст исключение в дополнение к созданию утверждения.  
  
 Макросы работать двумя способами, в зависимости от конфигурации проекта. Вызов макросов **ASSERT** и затем создает исключение, если утверждение не выполняется. Таким образом, в конфигурациях отладки (то есть слово **_DEBUG** определяется) макросы приводить утверждение и исключение в конфигурацию выпуска; макросы обеспечивает только исключение (**ASSERT** — нет вычислить выражение в конфигурациях выпуска).  
  
 Макрос **ENSURE_ARG** действует как **УБЕДИТЕСЬ, что** макрос.  
  
 **ENSURE_VALID** вызовы `ASSERT_VALID` макрос (который оказывает влияние только в отладочных построениях). Кроме того **ENSURE_VALID** вызывает исключение, если указатель имеет значение NULL. NULL тест выполняется в конфигурации отладки и выпуска.  
  
 Если любой из этих тестов завершается с ошибкой, так же, как отображается предупреждающее сообщение **ASSERT**. Макрос создает исключение недопустимого аргумента при необходимости.  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [ПРОВЕРЬТЕ](#verify)   
 [ATLENSURE](#altensure)

## <a name="this_file"></a> THIS_FILE
Имя файла, скомпилированного при развертывании.  
   
### <a name="syntax"></a>Синтаксис    
```
THIS_FILE    
```  
   
### <a name="remarks"></a>Примечания  
 Используемые сведения **ASSERT** и **ПРОВЕРЬТЕ** макросы. Мастер приложения и код мастеров поместите макрос в файлах исходного кода, которые они создают.  
   
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
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [ASSERT](#assert)   
 [VERIFY](#verify)


##  <a name="trace"></a>  TRACE  
 Отправляет указанную строку в отладчик текущего приложения.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) описание **ТРАССИРОВКИ**. **ТРАССИРОВКИ** и `ATLTRACE2` имеют одинаковое поведение.  
  
 В отладочной версии MFC этот макрос отправляет указанную строку отладчик текущего приложения. В сборке выпуска этот макрос компилируется в ничего (код не создается вообще).  
  
 Дополнительные сведения см. в разделе [отладки приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="verify"></a>  VERIFY  
 В отладочной версии MFC проверяет его аргумент.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Указывает выражение (включая значения указателя), результатом вычисления которого нуля или равен нулю.  
  
### <a name="remarks"></a>Примечания  
 Если результат равен 0, макрос выводит диагностическое сообщение и останавливает выполнение программы. Если условие имеет ненулевое значение, он не выполняет никаких действий.  
  
 Диагностическое сообщение имеет форму  
  
 `assertion failed in file <name> in line <num>`  
  
 где *имя* — имя исходного файла и *num* — это номер строки утверждения, завершившегося ошибкой в исходном файле.  
  
 В окончательной версии MFC **ПРОВЕРЬТЕ** вычисляет выражение, но не напечатать или прерывания работы программы. Например если выражение является вызов функции, будет выполнен вызов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  afxDump (CDumpContext в MFC)  
 Предоставляет базовые возможности формирование дампа объекта в приложении.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>Примечания  
 `afxDump` — Это стандартный [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объект, который позволяет отправлять `CDumpContext` данных в окне вывода или терминал отладки. Как правило, указывается `afxDump` как параметр `CObject::Dump`.  
  
 В Windows NT и всех версиях Windows `afxDump` выходные данные направляются в окно выходных данных отладки Visual C++ при отладке приложения.  
  
 Эта переменная определяется только в отладочной версии MFC. Дополнительные сведения о `afxDump`, в разделе [отладки приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h


## <a name="afxdump"></a> AfxDump (внутренний)
Внутренняя функция, который используется библиотекой MFC для помещения в дамп состояния объекта во время отладки.  

### <a name="syntax"></a>Синтаксис    
```
void AfxDump(const CObject* pOb);   
```
### <a name="parameters"></a>Параметры  
 `pOb`  
 Указатель на объект класса, производного от `CObject`.  
   
### <a name="remarks"></a>Примечания  
 **AfxDump** вызывает объект `Dump` функция-член и отправляет сведения в расположение указаны в `afxDump` переменной. **AfxDump** доступна только в отладочной версии MFC.  
  
 Программный код не должен вызывать **AfxDump**, но вместо этого необходимо вызвать `Dump` функции-члена объекта.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
   
### <a name="see-also"></a>См. также  
 [CObject::Dump](cobject-class.md#dump)   



##  <a name="afxmemdf"></a>  afxMemDF  
 Эта переменная доступна из отладчика или программы и позволяет клиентам настраивать диагностики распределения.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>Примечания  
 `afxMemDF` может иметь следующие значения, заданные в перечислении `afxMemDF`:  
  
- **allocMemDF** Включение отладки распределителя (по умолчанию в отладочной библиотеке).  
  
- **delayFreeMemDF** задерживает освобождение памяти. Пока приложение освобождает блок памяти, распределителя не возвращает эту память для операционной системы. Это разместите нагрузки максимальный объем памяти в приложении.  
  
- **checkAlwaysMemDF** вызовы `AfxCheckMemory` каждый раз при выделении или освобождении памяти. Это значительно снижает скорость операций выделения памяти и освобождения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError  
 Эта функция проверяет переданный **SCODE** ли ошибка.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>Примечания  
 Если это ошибка, функция создает исключение. Если переданный `SCODE` — **E_OUTOFMEMORY**, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) путем вызова [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). В противном случае функция создает [COleException](../../mfc/reference/coleexception-class.md) путем вызова [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Эта функция может использоваться для проверки возвращаемыми значениями вызовов функций OLE в приложении. Тестируя возвращаемое значение с помощью этой функции в приложении, может правильно реагировать на ошибки с минимальным объемом кода.  
  
> [!NOTE]
>  Эта функция действует так же при отладке, а не отладочные построения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory  
 Эта функция проверяет в пул свободной памяти и выводит сообщения об ошибках при необходимости.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если ошибки памяти; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если функция обнаруживает повреждение памяти, выводит ничего.  
  
 Проверяются все блоки памяти, выделенные в данный момент в куче, включая те, выделенной с помощью **новый** , но не те, которые выделены прямые вызовы базового выделения памяти, такие как `malloc` функции или  **GlobalAlloc** функции Windows. При обнаружении любого блока повреждены сообщение выводится в выходные данные отладчика.  
  
 Если включить строку  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 в модуле программы, затем последующие вызовы `AfxCheckMemory` Показать имя файла и номер строки, где была выделена память.  
  
> [!NOTE]
>  Если модуль содержит один или несколько реализаций сериализуемых классов, то необходимо поместить `#define` строки после последнего `IMPLEMENT_SERIAL` вызов макроса.  
  
 Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
 
##  <a name="afxdump"></a>  AfxDump (MFC)  
 Вызывайте эту функцию в отладчике для помещения в дамп состояния объекта во время отладки.  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>Параметры  
 `pOb`  
 Указатель на объект класса, производного от `CObject`.  
  
### <a name="remarks"></a>Примечания  
 **AfxDump** вызывает объект `Dump` функция-член и отправляет сведения в расположение указаны в `afxDump` переменной. **AfxDump** доступна только в отладочной версии MFC.  
  
 Программный код не должен вызывать **AfxDump**, но вместо этого необходимо вызвать `Dump` функции-члена объекта.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  

### <a name="see-also"></a>См. также  
 [CObject::Dump](cobject-class.md#dump)   


  
##  <a name="afxdumpstack"></a>  AfxDumpStack  
 Эту глобальную функцию, можно создавать образ текущего стека.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>Параметры  
 *dwTarget*  
 Указывает целевой выходные данные дампа. Возможные значения, которые могут быть объединены с помощью побитового или ( **&#124;**) оператор, таковы:  
  
- **AFX_STACK_DUMP_TARGET_TRACE** отправляет выходные данные с помощью параметра [ТРАССИРОВКИ](#trace) макрос. **ТРАССИРОВКИ** макрос создает выходные данные только для отладочных сборок; он не создает выходные данные в сборках выпуска. Кроме того **ТРАССИРОВКИ** может быть перенаправлен к другим целевым объектам, помимо отладчик.  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT** отправляет дампа выходные данные в целевой объект по умолчанию. Для отладочной сборки, результат выводится в **ТРАССИРОВКИ** макрос. В сборке выпуска результат выводится в буфер обмена.  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD** отправляет выходные данные только в буфер обмена. Данные помещаются в буфер обмена в виде обычного текста с помощью **CF_TEXT** формат буфера обмена.  
  
- **AFX_STACK_DUMP_TARGET_BOTH** отправляет выходные данные в буфер обмена, позволяющая **ТРАССИРОВКИ** макрос, одновременно.  
  
- **AFX_STACK_DUMP_TARGET_ODS** отправляет выходные данные непосредственно в окне отладчика с помощью функции Win32 **OutputDebugString()**. Этот параметр создаст выходных данных отладчика в обоих отладки и построения выпуска, если отладчик присоединен к процессу. **AFX_STACK_DUMP_TARGET_ODS** всегда достигает отладчика (если он подключен) и не может быть перенаправлен.  
  
### <a name="remarks"></a>Примечания  
 В приведенном ниже примере отражает одной строки выходных данных, полученных из вызова метода `AfxDumpStack` из обработчика кнопки в приложении MFC диалоговое окно:  
  
 `=== begin AfxDumpStack output ===`  
  
 `00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes`  
  
 `0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes`  
  
 `0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,`  
  
 `unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct AFX_CMDHANDLE`  
  
 `0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes`  
  
 `00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes`  
  
 `00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned`  
  
 `int,long) + 312 bytes`  
  
 `00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned`  
  
 `int,unsigned int,long,long *) + 83 bytes`  
  
 `00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned`  
  
 `int,unsigned int,long) + 46 bytes`  
  
 `004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct`  
  
 `HWND__ *,unsigned int,unsigned int,long) + 237 bytes`  
  
 `00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned`  
  
 `int,unsigned int,long) + 129 bytes`  
  
 `BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes`  
  
 `BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes`  
  
 `=== end AfxDumpStack() output ===`  
  
 Каждая строка в приведенном выше примере адрес последнем вызове функции, полный путь к модулю, содержащему вызов функции и прототип функции вызывается. Если вызов функции в стеке происходит не на адрес функции, отображается смещение байтов.  
  
 Например в следующей таблице описаны первая часть приведенных выше выходных данных:  
  
|Вывод|Описание|  
|------------|-----------------|  
|`00427D55:`|Обратный адрес последнем вызове функции.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|Полный путь к модулю, содержащему вызов функции.|  
|`void AfxDumpStack(unsigned long)`|Прототип функции вызывается.|  
|`+ 181 bytes`|Смещение в байтах от адреса прототип функции (в этом случае `void AfxDumpStack(unsigned long)`) в обратный адрес (в данном случае `00427D55`).|  
  
 `AfxDumpStack` доступна в версиях отладки и отладки библиотеки MFC; Однако функция всегда компонуется статически, даже в том случае, если исполняемый файл использует MFC в общей библиотеке DLL. В реализациях общую библиотеку функция находится в MFCS42. Библиотека LIB (и его вариантов).  
  
 Для успешного использования этой функции:  
  
-   Файл IMAGEHLP. Библиотеки DLL должны находиться в пути. Если у вас Эта библиотека DLL, функция отобразит сообщение об ошибке. В разделе [библиотеки справки образа](http://msdn.microsoft.com/library/windows/desktop/ms680321) сведения о наборе функции, предоставляемые IMAGEHLP.  
  
-   Модули, которые имеют кадров в стеке должны включать отладочную информацию. Если они не содержат сведения об отладке, функция будет по-прежнему создавать трассировку стека, но трассировка будет менее подробным.  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump  
 Включает и выключает дамп утечки памяти в деструкторе `AFX_DEBUG_STATE` .  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDump`  
 `TRUE` указывает, что дамп утечки памяти включен; `FALSE` указывает, что дамп утечки памяти отключен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение для этого флага.  
  
### <a name="remarks"></a>Примечания  
 Когда приложение выгружает библиотеку MFC, она выполняет проверку на наличие утечек памяти. На этом этапе любой утечки памяти отображаются пользователю через **отладки** окно [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Если приложение загружает другую библиотеку перед библиотекой MFC, некоторые выделения памяти в этой библиотеке ошибочно выводятся как утечки памяти. Ложные утечки памяти могут привести к медленному закрытию приложения, пока библиотека MFC сообщает о них. В этом случае воспользуйтесь `AfxEnableMemoryLeakDump` , чтобы отключить дамп утечки памяти.  
  
> [!NOTE]
>  При использовании этого метода для отключения дампа утечки памяти вы не будете получать отчеты о действительных утечках памяти в приложении. Этот метод следует использовать только в том случае, если вы уверены, что в отчете представлены только ложные утечки памяти.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking  
 Отслеживание диагностики памяти обычно включена в отладочной версии MFC.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>Параметры  
 *bTrack*  
 Установка этого значения в **TRUE** включает памяти; **FALSE** отключает его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущая Настройка флаг включения отслеживания.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для отключения отслеживания на фрагменты кода, вы знаете правильно выделения блоков.  
  
 Дополнительные сведения о `AfxEnableMemoryTracking`, в разделе [отладки приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxismemoryblock"></a>  AfxIsMemoryBlock  
 Проверяет, адрес памяти, чтобы убедиться, что он представляет блока активной памяти, который был выделен диагностики версией **новый**.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на блок памяти, которое необходимо проверить.  
  
 `nBytes`  
 Содержит длину блока памяти в байтах.  
  
 `plRequestNumber`  
 Указывает на **длинные** целое число, которое будет заполнено порядковый номер выделения блока памяти, или нуль, если он не представляет блок активной памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если блок памяти в настоящее время выделен, а длина — верным; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Он также проверяет указанный размер от исходного размера, выделенного. Если функция возвращает ненулевое значение, порядковый номер выделения возвращается в `plRequestNumber`. Это число представляет порядок, в котором был выделен блок относительно всех других **новый** распределения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxisvalidaddress"></a>  AfxIsValidAddress  
 Проверяет адреса памяти для обеспечения содержится целиком в пределах пространства памяти программы.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>Параметры  
 `lp`  
 Указывает на адрес в памяти, которое необходимо проверить.  
  
 `nBytes`  
 Содержит число байтов памяти, которое необходимо проверить.  
  
 *bReadWrite*  
 Указывает, является ли память и для чтения и записи ( **TRUE**) или только чтение ( **FALSE**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях ненулевое значение, если блок памяти указанного содержится целиком в пределах пространства памяти программы; в противном случае — 0.  
  
 В неотладочных сборках ненулевое значение, если `lp` не является NULL, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Адрес не ограничивается блоков, выделенной с помощью **новый**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxisvalidstring"></a>  AfxIsValidString  
 Эта функция используется для определения допустимости указателем на строку.  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>Параметры  
 `lpsz`  
 Указатель для тестирования.  
  
 `nLength`  
 Указывает длину строки, которое необходимо проверить, в байтах. Значение -1 показывает, что строка символом null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях, ненулевое значение, если заданный указатель указывает на строку указанного размера; в противном случае — 0.  
  
 В неотладочных сборках ненулевое значение, если `lpsz` не является NULL, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxsetallochook"></a>  AfxSetAllocHook  
 Задает обработчик, который включает вызов указанной функции перед выделенной каждого блока памяти.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>Параметры  
 *pfnAllocHook*  
 Задает имя вызываемой функции. См. заметки для прототипа функции выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вы хотите разрешить распределения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Распределитель памяти отладки библиотеки классов Microsoft Foundation можно вызвать функция-ловушка пользовательские разрешения пользователю для отслеживания выделения памяти и управления, разрешено ли выделение. Прототипы функций-ловушек выделения следующим образом:  
  
 **BOOL AFXAPI AllocHook (size_t** `nSize` **, BOOL** `bObject` **, LONG** `lRequestNumber` **);**  
  
 `nSize`  
 Размер выделения памяти предложенный.  
  
 `bObject`  
 **Значение TRUE,** Если выделено для `CObject`-производный объект; в противном случае **FALSE**.  
  
 `lRequestNumber`  
 Порядковый номер выделения памяти.  
  
 Обратите внимание, что **AFXAPI** соглашение о вызовах означает, что вызываемый объект необходимо удалить параметры из стека.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses  
 Вызывает функцию определенной итерации для всех сериализуемых `CObject`-производные классы в пространстве памяти приложения.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Параметры  
 `pfn`  
 Указывает на итерацию функция, вызываемая для каждого класса. Эти аргументы функции не указатель на `CRuntimeClass` объект и указатель void на дополнительные данные, вызывающий предоставляет функции.  
  
 `pContext`  
 Указывает дополнительные данные, которые вызывающий объект может предоставить функцию итерации. Этот указатель может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Сериализуемые `CObject`-производные классы являются классы, производные с использованием `DECLARE_SERIAL` макрос. Указатель, который передается `AfxDoForAllClasses` в `pContext` передается в функцию определенной итерации при каждом вызове.  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects  
 Выполняет функцию определенной итерации для всех объектов, производных от `CObject` , была выделена с **новый**.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Параметры  
 `pfn`  
 Указывает функцию итерации для выполнения для каждого объекта. Эти аргументы функции не указатель на `CObject` и указатель void на дополнительные данные, вызывающий предоставляет функции.  
  
 `pContext`  
 Указывает дополнительные данные, которые вызывающий объект может предоставить функцию итерации. Этот указатель может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Стек, глобальная или внедренных объектов, не перечисляются. Указатель, передаваемый `AfxDoForAllObjects` в `pContext` передается в функцию определенной итерации при каждом вызове.  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)