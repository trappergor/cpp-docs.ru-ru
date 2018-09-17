---
title: Диагностические службы | Документация Майкрософт
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
ms.openlocfilehash: 6d3adeff7c0c242d9e83b2e71afff78ec130f950
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712962"
---
# <a name="diagnostic-services"></a>Диагностические службы
Библиотека Microsoft Foundation Class предоставляет множество служб диагностики, которые упрощают отладку программ. Эти службы включают в себя макросы и глобальные функции, позволяющие отслеживать выделение памяти для программы, записывать дамп содержимого объектов во время выполнения и печатать сообщения отладки во время выполнения. Макросы и глобальные функции диагностических служб сгруппированы в следующие категории:  
  
-   общие диагностические макросы;  
  
-   общие диагностические функции и переменные;  
  
-   функции диагностики объектов.  
  
 Эти макросы и функции доступны для всех классов, производных от `CObject` , в отладочной и окончательной версиях MFC. Тем не менее, все, кроме DEBUG_NEW и ПРОВЕРИТЬ ничего не делать в окончательной версии.  
  
 В отладочной библиотеке все блоки выделенной памяти заключаются в последовательности "защитных байтов". Если эти байты изменяются в результате ошибочной операции записи в память, диагностические подпрограммы могут сообщить о проблеме. Если включить строку:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 в файл реализации, все вызовы **new** будут сохранять имя файла и номер строки, в которой выполняется выделение памяти. Функция [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) будет выводить дополнительную информацию, позволяющую выявить утечки памяти. Дополнительные сведения о выходных диагностических данных см. также в описании класса [CDumpContext](../../mfc/reference/cdumpcontext-class.md) .  
  
 Кроме того, библиотека времени выполнения C также поддерживает ряд диагностических функций, которые можно использовать для отладки приложений. Дополнительные сведения см. в разделе [Подпрограммы отладки](../../c-runtime-library/debug-routines.md) справочника по библиотеке времени выполнения.  
  
### <a name="mfc-general-diagnostic-macros"></a>Общие диагностические макросы MFC  
  
|||  
|-|-|  
|[ASSERT](#assert)|Выводит сообщение и затем прерывает выполнение программы, если указанное выражение принимает значение FALSE в отладочной версии библиотеки.|  
|[ASSERT_KINDOF](#assert_kindof)|Проверяет, является ли объект объектом указанного класса или класса, производного от указанного.|  
|[ASSERT_VALID](#assert_valid)|Проверяет внутреннюю допустимость объекта, вызывая его функцию-член `AssertValid` ; обычно переопределяется из `CObject`.|
|[DEBUG_NEW](#debug_new)|Предоставляет имя файла и номер строки для каждого выделения объекта в режиме отладки для выявления утечек памяти.|  
|[DEBUG_ONLY](#debug_only)|Аналогичную ASSERT, но не проверяет значение выражения; полезно для кода, который должен выполняться только в режиме отладки.|  
|[Убедитесь, ЧТО и ENSURE_VALID](#ensure)|Используйте для проверки правильности данных.|
|[THIS_FILE](#this_file)|Имя файла, скомпилированного при развертывании.|
|[TRACE](#trace)|Работает аналогично `printf`в отладочной версии библиотеки.|  
|[VERIFY](#verify)|Аналогично ASSERT, но вычисляет выражение в окончательной версии библиотеки, а также в отладочной версии.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>Общие диагностические переменные и функции MFC  
  
|||  
|-|-|  
|[afxDump](#afxdump)|Глобальная переменная, которая отправляет информацию [CDumpContext](../../mfc/reference/cdumpcontext-class.md) в окно выходных данных отладчика или в терминал отладки.|  
|[afxMemDF](#afxmemdf)|Глобальная переменная, которая управляет поведением отладочного распределителя памяти.|  
|[AfxCheckError](#afxcheckerror)|Глобальная переменная, используемая для проверки переданного SCODE ли является ошибкой, и если да, вызывается соответствующая ошибка.|  
|[AfxCheckMemory](#afxcheckmemory)|Проверяет целостность всей выделенной на текущий момент памяти.|  
|[AfxDebugBreak](#afxdebugbreak)|Вызывает прерывание выполнения.|
|[AfxDump](#cdumpcontext_in_mfc)|При вызове в отладчике записывает дамп состояния объекта в процессе отладки.|  
|[AfxDump](#afxdump)|Внутренняя функция, которая записывает дамп состояния объекта во время отладки.|
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

### <a name="mfc-compilation-macros"></a>Макросы MFC компиляции
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
 Следующий код вызовет предупреждение компилятора, если _AFX_SECURE_NO_WARNINGS не определены.  
  
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

## <a name="afxdebugbreak"></a> AfxDebugBreak
Вызывайте эту функцию для отменяется (в месте вызова `AfxDebugBreak`) при выполнении отладочной версии приложения MFC.  

### <a name="syntax"></a>Синтаксис    
```
void AfxDebugBreak( );    
```  
   
### <a name="remarks"></a>Примечания  
 `AfxDebugBreak` не оказывает влияния в версии приложения MFC и должна быть удалена. Эта функция должна использоваться только в приложениях MFC. Используйте версию Win32 API, `DebugBreak`, в результате чего разрыв в приложениях, не использующих MFC.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxver_.h   

##  <a name="assert"></a>  ASSERT
 Оценивает своего аргумента.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>Параметры  
 *booleanExpression*  
 Указывает выражение (включая значения указателя), результатом вычисления которого нуля или равен нулю.  
  
### <a name="remarks"></a>Примечания  
 Если результат равен 0, макрос выводит диагностическое сообщение и прерывает выполнение программы. Если условие имеет ненулевое значение, ничего не происходит.  
  
 Диагностическое сообщение имеет форму  
  
 `assertion failed in file <name> in line <num>`  
  
 где *имя* имя исходного файла и *num* — это номер строки утверждения, сбой в исходном файле.  
  
 В финальной версии MFC ASSERT не вычисляет выражение и таким образом, не будет прерван программы. Если необходимо вычислить выражение независимо от среды, используйте макрос VERIFY вместо ASSERT.  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="assert_kindof"></a>  ASSERT_KINDOF  
 Этот макрос утверждает, что объект, на который указывает объект указанного класса или является объект класса, производного от указанного класса.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>Параметры  
 *classname*  
 Имя `CObject`-производного класса.  
  
 *pObject*  
 Указатель на объект класса.  
  
### <a name="remarks"></a>Примечания  
 *Pobject* параметр должен быть указателем на объект и может быть **const**. Указывает объект и класс должен поддерживать `CObject` сведения о классе во время выполнения. Например, чтобы убедиться, что `pDocument` — это указатель на объект `CMyDoc` класса или любого из его производных кода:  
  
 [!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 С помощью `ASSERT_KINDOF` макрос именно это отличается от программирования:  
  
 [!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 Эта функция работает только для классов, объявленных с [DECLARE_DYNAMIC] (#declare_dynamic выполнения время объект модели services.md или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.  
  
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
 *pObject*  
 Указывает объект класса, производного от `CObject` с переопределение `AssertValid` функция-член.  
  
### <a name="remarks"></a>Примечания  
 Вызовы ASSERT_VALID `AssertValid` функция-член объекта, переданный в качестве аргумента.  
  
 В версии MFC ASSERT_VALID не выполняет никаких действий. В отладочной версии, проверяется указатель, проверяет наличие значения NULL и вызывает собственный `AssertValid` функций-членов. Если любой из этих тестов завершается ошибкой, предупреждающее сообщение отображается в так же, как [ASSERT](#assert).  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  
  
 Дополнительные сведения и примеры см. в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
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
 DEBUG_NEW можно использовать везде в приложении, обычно применяются **новый** оператор для выделения памяти кучи.  
  
 В режиме отладки (когда **_DEBUG** определен символ), DEBUG_NEW следит за имя файла и номер строки для каждого объекта, которому выделяется память. Затем, при использовании [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) функции-члена каждого объекта выделяется с помощью DEBUG_NEW отображаемое имя файла и номер строки, где было выполнено выделение.  
  
 Чтобы использовать DEBUG_NEW, вставьте следующую директиву в исходные файлы:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 После добавления этой директивы препроцессора вставит DEBUG_NEW, при любом использовании **новый**, а MFC делает все остальное. При компиляции окончательной версии программы DEBUG_NEW простой **новый** операцию и имя файла и номере строки не создаются.  
  
> [!NOTE]
>  В предыдущих версиях MFC (версии 4.1 и более ранних версий) требовалось размещать `#define` инструкции после всех инструкций, которые вызваны IMPLEMENT_DYNCREATE или IMPLEMENT_SERIAL макросы. Это больше не требуется.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY  
 В режиме отладки (когда **_DEBUG** определен символ), DEBUG_ONLY оценивает своего аргумента.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>Примечания  
 В окончательном построении DEBUG_ONLY его аргумент не вычисляется. Это полезно в тех случаях, когда у вас есть код, который должен быть выполнен только в отладочных сборках.  
  
 Debug_only-макрос эквивалентен вокруг *выражение* с `#ifdef _DEBUG` и `#endif`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

 ### <a name="ensure"></a>  Убедитесь, ЧТО и ENSURE_VALID
Используйте для проверки правильности данных.  
   
### <a name="syntax"></a>Синтаксис    
```
ENSURE(  booleanExpression )  
ENSURE_VALID( booleanExpression  )  
```
### <a name="parameters"></a>Параметры  
 *booleanExpression*  
 Указывает логическое выражение, проверяемое.  
   
### <a name="remarks"></a>Примечания  
 Эти макросы предназначена для улучшения проверки параметров. Макросы не, дальнейшая обработка неверные параметры в коде. В отличие от макрос ASSERT убедитесь, ЧТО макросы исключение в дополнение к созданию утверждение.  
  
 Макросы ведут себя двумя способами, в соответствии с конфигурацией проекта. Макросы вызвать ASSERT и затем выдавал исключение, если утверждение не выполняется. Таким образом в конфигурациях отладки (то есть слово _DEBUG определен) макросы сформировать утверждение и возникло исключение при в конфигурациях выпуска, макросы создают только исключение (ASSERT не вычислить выражение в конфигурациях выпуска).  
  
 Макрос ENSURE_ARG выступает в роли убедитесь, ЧТО макрос.  
  
 ENSURE_VALID вызывает макрос ASSERT_VALID (который оказывает влияние только в отладочных сборках). Кроме того ENSURE_VALID создает исключение, если указатель имеет значение NULL. Данная проверка NULL выполняется в конфигурации отладки и выпуска.  
  
 При сбое любой из этих проверок, предупреждающее сообщение отображается в так же, как ASSERT. Макрос создает исключение недопустимого аргумента, при необходимости.  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [ПРОВЕРКА](#verify)   
 [ATLENSURE](#altensure)

## <a name="this_file"></a> THIS_FILE
Имя файла, скомпилированного при развертывании.  
   
### <a name="syntax"></a>Синтаксис    
```
THIS_FILE    
```  
   
### <a name="remarks"></a>Примечания  
 Сведения, используются макросы ASSERT и ПРОВЕРИТЬ. Мастера мастер приложения и кода поместите макрос в файлах исходного кода, которые они создают.  
   
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
 Отправляет указанную строку в отладчике текущего приложения.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) описание ТРАССИРОВКИ. ТРАССИРОВКИ и ATLTRACE2 ведут себя так же.  
  
 В отладочной версии MFC этот макрос отправляет указанную строку в отладчик текущего приложения. В сборке выпуска этот макрос компилируется в ничего (код не создается вообще).  
  
 Дополнительные сведения см. в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="verify"></a>  VERIFY  
 В отладочной версии MFC вычисляет его аргумент.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>Параметры  
 *booleanExpression*  
 Указывает выражение (включая значения указателя), результатом вычисления которого нуля или равен нулю.  
  
### <a name="remarks"></a>Примечания  
 Если результат равен 0, макрос выводит диагностическое сообщение и останавливает выполнение программы. Если условие имеет ненулевое значение, ничего не происходит.  
  
 Диагностическое сообщение имеет форму  
  
 `assertion failed in file <name> in line <num>`  
  
 где *имя* имя исходного файла и *num* — это номер строки утверждения, сбой в исходном файле.  
  
 В финальной версии MFC ПРОВЕРЬТЕ вычисляет выражение, но не печати или прерывание программы. К примеру Если выражение является вызовом функции, будет выполнен вызов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  afxDump (CDumpContext в MFC)  
 Предоставляет основные возможности формирование дампа объекта в приложении.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>Примечания  
 `afxDump` — Это стандартный [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объект, который можно отправить `CDumpContext` сведения в окне вывода отладчика или в терминал отладки. Как правило, вы указали `afxDump` в качестве параметра `CObject::Dump`.  
  
 В Windows NT и всех версиях Windows `afxDump` вывод направляется в окно вывода отладки Visual C++ при отладке приложения.  
  
 Эта переменная определена только в отладочной версии MFC. Дополнительные сведения о `afxDump`, см. в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h


## <a name="afxdump"></a> AfxDump (внутренний)
Внутренняя функция, которая использует MFC для помещения в дамп состояния объекта во время отладки.  

### <a name="syntax"></a>Синтаксис    
```
void AfxDump(const CObject* pOb);   
```
### <a name="parameters"></a>Параметры  
 *почтовый ящик*  
 Указатель на объект класса, производного от `CObject`.  
   
### <a name="remarks"></a>Примечания  
 `AfxDump` вызывает объект `Dump` функция-член и отправляет данные в расположение, определяемое `afxDump` переменной. `AfxDump` доступен только в отладочной версии MFC.  
  
 Код программы не следует вызывать `AfxDump`, но вместо этого необходимо вызвать `Dump` функции-члена объекта.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
   
### <a name="see-also"></a>См. также  
 [CObject::Dump](cobject-class.md#dump)   



##  <a name="afxmemdf"></a>  afxMemDF  
 Эта переменная, доступен из отладчика или программы и позволяет настраивать диагностики распределения.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>Примечания  
 `afxMemDF` может иметь следующие значения, указанные в перечислении `afxMemDF`:  
  
- `allocMemDF` Включение отладки распределителя (по умолчанию в отладочной библиотеке).  
  
- `delayFreeMemDF` Задержки при освобождении памяти. Хотя программа освобождает блок памяти, распределитель не возвращает эту память для операционной системы. Это поместите stress максимальный объем памяти в приложении.  
  
- `checkAlwaysMemDF` Вызовы `AfxCheckMemory` каждый раз при выделении или освобождении памяти. Это значительно снижает скорость операций выделения памяти и освобождения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError  
 Эта функция проверяет переданный SCODE, является ли ошибка.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>Примечания  
 Если это ошибка, функция создает исключение. Если переданный SCODE E_OUTOFMEMORY, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) путем вызова [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). В противном случае функция создает [COleException](../../mfc/reference/coleexception-class.md) путем вызова [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Эта функция может использоваться для проверки возвращаемые значения для вызовов функций OLE в приложении. Тестирование возвращаемое значение с помощью этой функции в приложении, правильно реагировать на ошибки с минимальным объемом кода.  
  
> [!NOTE]
>  Эта функция действует так же в режиме отладки и выполняет построение без отладки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory  
 Эта функция проверяет пул свободной памяти и выводит сообщения об ошибках при необходимости.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если ошибки не памяти; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Если функция обнаруживает повреждение памяти, оно выводится ничего.  
  
 Проверяются все блоки памяти, выделенных в данный момент в куче, в том числе распределен **новый** но не распределен прямые вызовы базовых механизмов выделения памяти, таких как **malloc** функции или `GlobalAlloc` функции Windows. При обнаружении любой блок поврежден сообщение выводится в выходные данные отладчику.  
  
 Если включить строку  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 в программный модуль, а затем последующие вызовы `AfxCheckMemory` Показать имя файла и номер строки, где была выделена память.  
  
> [!NOTE]
>  Если модуль содержит один или несколько реализаций сериализуемых классов, то необходимо поместить `#define` строки после последнего вызова макроса IMPLEMENT_SERIAL.  
  
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
 *почтовый ящик*  
 Указатель на объект класса, производного от `CObject`.  
  
### <a name="remarks"></a>Примечания  
 `AfxDump` вызывает объект `Dump` функция-член и отправляет данные в расположение, определяемое `afxDump` переменной. `AfxDump` доступен только в отладочной версии MFC.  
  
 Код программы не следует вызывать `AfxDump`, но вместо этого необходимо вызвать `Dump` функции-члена объекта.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  

### <a name="see-also"></a>См. также  
 [CObject::Dump](cobject-class.md#dump)   


  
##  <a name="afxdumpstack"></a>  AfxDumpStack  
 Этой глобальной функции можно создавать образ текущего стека.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>Параметры  
 *dwTarget*  
 Указывает цель выходные данные дампа. Возможные значения, которые можно комбинировать с помощью побитового или ( **&#124;**), имеют следующим образом:  
  
- AFX_STACK_DUMP_TARGET_TRACE отправляет выходные данные с помощью параметра [ТРАССИРОВКИ](#trace) макрос. Макрос TRACE создает выходные данные в отладочных сборках. он не создает выходные данные в сборках выпуска. Кроме того можно перенаправить ТРАССИРОВКИ к другим целевым объектам, помимо отладчика.  
  
- AFX_STACK_DUMP_TARGET_DEFAULT отправляет выходные данные дампа в целевой объект по умолчанию. Для отладочной сборки выводе макрос TRACE. В сборке выпуска вывод идет в буфер обмена.  
  
- AFX_STACK_DUMP_TARGET_CLIPBOARD отправляет выходные данные только в буфер обмена. Данные помещаются в буфер обмена как обычный текст, используя формат буфера обмена CF_TEXT.  
  
- AFX_STACK_DUMP_TARGET_BOTH отправляет выходные данные в буфер обмена и макрос TRACE, одновременно.  
  
- AFX_STACK_DUMP_TARGET_ODS отправляет выходные данные непосредственно в отладчике с помощью функции Win32 `OutputDebugString()`. Этот параметр создает выходных данных отладчика в обоих отладки и сборки выпуска при присоединении отладчика к процессу. AFX_STACK_DUMP_TARGET_ODS всегда достигнет отладчик (если он подключен) и не может быть перенаправлен.  
  
### <a name="remarks"></a>Примечания  
 В приведенном ниже примере отражает одной строки выходных данных, полученных из вызова метода `AfxDumpStack` из обработчика кнопки в диалоговом окне MFC-приложении:  
  
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
  
 Каждая строка в приведенном выше примере адрес последнего вызова функции, имя модуля, содержащего вызов функции и прототип функции вызывается полный путь. Если вызов функции в стеке происходит не на адрес функции, отображается смещение байтов.  
  
 Например в следующей таблице описаны первая часть приведенных выше выходных данных:  
  
|Вывод|Описание|  
|------------|-----------------|  
|`00427D55:`|Обратный адрес последнего вызова функции.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|Полный путь имя модуля, содержащего вызов функции.|  
|`void AfxDumpStack(unsigned long)`|Вызывается прототип функции.|  
|`+ 181 bytes`|Смещение в байтах от адреса прототип функции (в этом случае `void AfxDumpStack(unsigned long)`) по обратному адресу (в этом случае `00427D55`).|  
  
 `AfxDumpStack` доступно в версиях отладки и отладки библиотеки MFC; Тем не менее функция всегда компонуется статически, даже в том случае, если исполняемый файл использует MFC в общей DLL. В библиотеке общих реализаций функция находится в MFCS42. Библиотеки LIB (и его вариантов).  
  
 Для успешного использования этой функции:  
  
-   Файл IMAGEHLP. Библиотеки DLL должны находиться в пути. Если у вас нет этой библиотеки DLL, функция отобразит сообщение об ошибке. См. в разделе [библиотеки справки образа](/windows/desktop/Debug/image-help-library) сведения о наборе функций, предоставляемых IMAGEHLP.  
  
-   Модули, которые имеют кадров в стеке необходимо включить отладочную информацию. Если они не содержат сведения об отладке, функция по-прежнему создает трассировку стека, но трассировка будет менее подробным.  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump  
 Включает и выключает дамп утечки памяти в деструкторе AFX_DEBUG_STATE.  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>Параметры  
*bDump*<br/>
[in] Значение TRUE указывает, что дамп утечки памяти включен; Значение FALSE указывает, что дамп утечки памяти отключен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение для этого флага.  
  
### <a name="remarks"></a>Примечания  
 Когда приложение выгружает библиотеку MFC, она выполняет проверку на наличие утечек памяти. На этом этапе любых утечках памяти сообщается пользователю через **Отладка** окно Visual Studio.  
  
 Если приложение загружает другую библиотеку перед библиотекой MFC, некоторые выделения памяти в этой библиотеке ошибочно выводятся как утечки памяти. Ложные утечки памяти могут привести к медленному закрытию приложения, пока библиотека MFC сообщает о них. В этом случае воспользуйтесь `AfxEnableMemoryLeakDump` , чтобы отключить дамп утечки памяти.  
  
> [!NOTE]
>  При использовании этого метода для отключения дампа утечки памяти вы не будете получать отчеты о действительных утечках памяти в приложении. Этот метод следует использовать только в том случае, если вы уверены, что в отчете представлены только ложные утечки памяти.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking  
 Как правило, отслеживание диагностики памяти включена в отладочной версии MFC.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>Параметры  
 *bTrack*  
 Значение TRUE включает в памяти; FALSE его отключает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение флага включения отслеживания.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для отключения отслеживания на фрагменты кода, которые известны как выделяем блоков.  
  
 Дополнительные сведения о `AfxEnableMemoryTracking`, см. в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxismemoryblock"></a>  AfxIsMemoryBlock  
 Проверяет адрес памяти, чтобы убедиться в том, он представляет блок активной памяти, который был выделен функцией диагностики версии **новый**.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указывает на блок памяти, который необходимо протестировать.  
  
 *nBytes*  
 Содержит длину блока памяти в байтах.  
  
 *plRequestNumber*  
 Указывает на **long** целое число, которое будет заполнено порядковый номер выделения блока памяти, или нуль, если он не представляет блок активной памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если блок памяти, который сейчас находится группа и длина верно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Он также проверяет указанный размер от исходного размера, выделенного. Если функция возвращает ненулевое значение, порядковый номер выделения возвращается в *plRequestNumber*. Этот номер представляет порядок, в котором был выделен блок относительно всех других **новый** выделения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxisvalidaddress"></a>  AfxIsValidAddress  
 Проверяет, любой адрес памяти, чтобы убедиться, что он содержится целиком в пределах пространства памяти программы.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>Параметры  
 *к пулу журналов*  
 Указывает проверяемый адрес памяти.  
  
 *nBytes*  
 Содержит число байтов памяти, который необходимо протестировать.  
  
 *bReadWrite*  
 Указывает, является ли память как для чтения и записи (TRUE) или только чтение (FALSE).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных сборках ненулевое значение, если блокировать указанную память является полностью находящийся внутри пространства памяти программы; в противном случае 0.  
  
 В неотладочных сборках отличное от нуля значение *lp* не равно NULL; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Адрес не привязана к блокам, выделенной с помощью **новый**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxisvalidstring"></a>  AfxIsValidString  
 Эта функция используется для определения, является ли допустимым указателем на строку.  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>Параметры  
 *lpsz*  
 Указатель для тестирования.  
  
 *nLength*  
 Указывает длину строки, которое необходимо проверить, в байтах. Значение -1 указывает, что строка будет оканчиваться нулевым символом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных сборках, ненулевое значение, если заданный указатель указывает на строку указанного размера; в противном случае 0.  
  
 В неотладочных сборках отличное от нуля значение *lpsz* не равно NULL; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxsetallochook"></a>  AfxSetAllocHook  
 Задает обработчик, который включает вызов указанной функции, перед выделяется каждый блок памяти.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>Параметры  
 *pfnAllocHook*  
 Указывает имя вызываемой функции. См. в разделе "Примечания" для прототипа функции выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вы хотите разрешить выделение; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Распределитель памяти отладочной библиотеке Microsoft Foundation Class можно вызвать функция-обработчик, определяемые пользователем разрешения пользователю для отслеживания выделения памяти и управления, разрешено ли выделение. Ниже приведены прототипом функции-ловушки выделения.  
  
 **BOOL AFXAPI AllocHook (size_t** `nSize` **, BOOL** `bObject` **длинная** `lRequestNumber` **);**  
  
 *nSize*  
 Размер выделения предлагаемых памяти.  
  
 *bObject*  
 Значение TRUE, если выделение для `CObject`-производного объекта; в противном случае — FALSE.  
  
 *lRequestNumber*  
 Порядковый номер выделения памяти.  
  
 Обратите внимание на то, что подразумевает, что вызываемый объект необходимо удалить параметры из стека AFXAPI, соглашение о вызовах.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses  
 Вызывает функцию определенной итерации для все сериализуемые `CObject`-производные классы в пространстве памяти приложения.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Параметры  
 *pfn-имени*  
 Указывает функцию итерации, которую необходимо вызывать для каждого класса. Эти аргументы функции не указатель на `CRuntimeClass` объект и указатель void на дополнительные данные, которые вызывающий объект передает в функцию.  
  
 *pContext*  
 Указывает дополнительные данные, которые вызывающий объект может предоставить функции итерации. Этот указатель может иметь значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Сериализуемые `CObject`-производные классы рассматриваются как классы, производные с использованием declare_serial-макрос. Указатель, который передается `AfxDoForAllClasses` в *pContext* передается в функцию определенной итерации при каждом вызове.  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects  
 Выполняет функцию определенной итерации для всех объектов, производных от `CObject` , были выделены с помощью **новый**.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Параметры  
 *pfn-имени*  
 Указывает функцию итерации для выполнения для каждого объекта. Эти аргументы функции не указатель на `CObject` и указатель void на дополнительные данные, которые вызывающий объект передает в функцию.  
  
 *pContext*  
 Указывает дополнительные данные, которые вызывающий объект может предоставить функции итерации. Этот указатель может иметь значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Стек, глобальной или внедренные объекты, не перечисляются. Указатель передан в `AfxDoForAllObjects` в *pContext* передается в функцию определенной итерации при каждом вызове.  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)