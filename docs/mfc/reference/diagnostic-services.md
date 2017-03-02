---
title: "Диагностические службы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- diagnosis, diagnostic services
- diagnostic macros, list of general MFC
- services, diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables
- diagnostics, diagnostic functions and variables
- diagnostics, list of general MFC
- diagnosis, diagnostic functions and variables
- diagnosis, list of general MFC
- general diagnostic macros in MFC
- diagnostic macros
- diagnostic services
- object diagnostic functions in MFC
- diagnostics, diagnostic services
- diagnostic functions and variables
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 86fe366a4d7863fb9339b7b5a9f880103876de33
ms.lasthandoff: 02/24/2017

---
# <a name="diagnostic-services"></a>Диагностические службы
Библиотека Microsoft Foundation Class предоставляет множество служб диагностики, которые упрощают отладку программ. Эти службы включают в себя макросы и глобальные функции, позволяющие отслеживать выделение памяти для программы, записывать дамп содержимого объектов во время выполнения и печатать сообщения отладки во время выполнения. Макросы и глобальные функции диагностических служб сгруппированы в следующие категории:  
  
-   общие диагностические макросы;  
  
-   общие диагностические функции и переменные;  
  
-   функции диагностики объектов.  
  
 Эти макросы и функции доступны для всех классов, производных от `CObject` в версиях отладки и выпуска MFC. Тем не менее, все, кроме `DEBUG_NEW` и **ПРОВЕРИТЬ** ничего не в окончательной версии.  
  
 В отладочной библиотеке все блоки выделенной памяти заключаются в последовательности "защитных байтов". Если эти байты изменяются в результате ошибочной операции записи в память, диагностические подпрограммы могут сообщить о проблеме. Если включить строку:  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 в файле реализации всех вызовах **новый** сохранит имя файла и номер строки, где выполнялась выделения памяти. Функция [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) будет отображать эту дополнительную информацию, позволяя выявить утечки памяти. Также ссылаться на класс [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Дополнительные сведения о результатах диагностики.  
  
 Кроме того, библиотека времени выполнения C также поддерживает ряд диагностических функций, которые можно использовать для отладки приложений. Дополнительные сведения см. в разделе [процедуры отладки](../../c-runtime-library/debug-routines.md) в справочнике библиотеки времени выполнения.  
  
### <a name="mfc-general-diagnostic-macros"></a>Общие диагностические макросы MFC  
  
|||  
|-|-|  
|[УТВЕРЖДЕНИЕ](#assert)|Выводит сообщение, а затем прерывает выполнение программы, если заданное выражение оценивается как **FALSE** отладочной версией библиотеки.|  
|[ASSERT_KINDOF](#assert_kindof)|Проверяет, является ли объект объектом указанного класса или класса, производного от указанного.|  
|[ASSERT_VALID](#assert_valid)|Проверяет действительность внутреннего объекта путем вызова его `AssertValid` функция-член; как правило переопределенный из `CObject`.|  
|[DEBUG_NEW](#debug_new)|Предоставляет имя файла и номер строки для каждого выделения объекта в режиме отладки для выявления утечек памяти.|  
|[DEBUG_ONLY](#debug_only)|Аналогично **ASSERT** , но не проверяется значение выражения, полезно для кода, который должен выполняться только в режиме отладки.|  
|[TRACE](#trace)|Предоставляет `printf`-как возможность отладочной версией библиотеки.|  
|[ПРОВЕРКА](#verify)|Аналогично **ASSERT** , но результатом вычисления выражения в финальной версии библиотеки, также как и в отладочной версии.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>Общие диагностические переменные и функции MFC  
  
|||  
|-|-|  
|[afxDump](#afxdump)|Глобальная переменная, которая отправляет [CDumpContext](../../mfc/reference/cdumpcontext-class.md) сведений в окне вывода или терминалов отладки.|  
|[afxMemDF](#afxmemdf)|Глобальная переменная, которая управляет поведением отладочного распределителя памяти.|  
|[AfxCheckError](#afxcheckerror)|Глобальная переменная используется для проверки переданной **SCODE** ли он ошибки и, если да, вызывает соответствующую ошибку.|  
|[AfxCheckMemory](#afxcheckmemory)|Проверяет целостность всей выделенной на текущий момент памяти.|  
|[AfxDump](#cdumpcontext_in_mfc_)|При вызове в отладчике записывает дамп состояния объекта в процессе отладки.|  
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
|[AfxDoForAllClasses](#afxdoforallclasses)|Выполняет указанную функцию на всех `CObject`-производные классы, которые поддерживают проверку типа во время выполнения.|  
|[AfxDoForAllObjects](#afxdoforallobjects)|Выполняет указанную функцию на всех `CObject`-производных объектов, выделенных с **новый**.|  
  
##  <a name="a-nameasserta--assert"></a><a name="assert"></a>УТВЕРЖДЕНИЕ
 Проверяет его аргумент.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Указывает выражение (включая значения указателя), результатом которого является нуля или равен нулю.  
  
### <a name="remarks"></a>Примечания  
 Если результат равен 0, макрос выводит диагностическое сообщение и прерывает выполнение программы. Если условие имеет ненулевое значение, он не выполняет никаких действий.  
  
 Диагностическое сообщение имеет форму  
  
 `assertion failed in file <name> in line <num>`  
  
 где *имя* — имя исходного файла и *num* — это номер строки утверждения, сбой в исходном файле.  
  
 В окончательной версии MFC **ASSERT** не вычисляет выражение и таким образом не будет прерван программы. Если выражение должно быть независимо от среды, используйте **проверка** макрос вместо **ASSERT**.  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#44;](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameassertkindofa--assertkindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF  
 Этот макрос утверждает, что объект, на который указывает объект указанного класса или является объект класса, производным от указанного класса.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>Параметры  
 *className*  
 Имя `CObject`-производного класса.  
  
 *pObject*  
 Указатель на объект класса.  
  
### <a name="remarks"></a>Примечания  
 *Pobject* параметр должен быть указателем на объект и может быть **const**. Указывает объект, а класс должен поддерживать `CObject` сведения о классе во время выполнения. Например, чтобы убедиться, что `pDocument` является указателем на объект `CMyDoc` класса или любого из его производных кода:  
  
 [!code-cpp[NVC_MFCDocView&#194;](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 С помощью `ASSERT_KINDOF` макрос совпадает кодирования:  
  
 [!code-cpp[NVC_MFCDocView&#195;](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 Эта функция работает только для классов, объявленные с [DECLARE_DYNAMIC] (#declare_dynamic запуск время объект модели services.md или [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос.  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameassertvalida--assertvalid"></a><a name="assert_valid"></a>ASSERT_VALID  
 Используется для проверки своих предположений о допустимости внутреннего состояния объекта.  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указывает объект, производный от класса `CObject` с переопределение `AssertValid` функции-члена.  
  
### <a name="remarks"></a>Примечания  
 `ASSERT_VALID`вызовы `AssertValid` функции-члена объекта передается в качестве своего аргумента.  
  
 В окончательной версии MFC `ASSERT_VALID` не выполняет никаких действий. В отладочной версии проверки указателя, проверяет **NULL**и вызывает объекта собственные `AssertValid` функции-члены. Если любой из этих тестов завершается с ошибкой, так же, как отображается предупреждающее сообщение [ASSERT](#assert).  
  
> [!NOTE]
>  Эта функция доступна только в отладочной версии MFC.  
  
 Дополнительные сведения и примеры см. в разделе [отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&19;](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-namedebugnewa--debugnew"></a><a name="debug_new"></a>DEBUG_NEW  
 Помогает обнаружить утечки памяти.  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `DEBUG_NEW` везде в приложении, которые обычно используются **новый** оператор для выделения памяти в куче.  
  
 В режиме отладки (когда **_DEBUG** символ определен), `DEBUG_NEW` продолжает отслеживания из файла и номер строки для каждого объекта, которому выделяется память. Затем, при использовании [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) выделить каждый объект функции-члена с `DEBUG_NEW` отображается имя файла и номер строки, где было выполнено выделение.  
  
 Для использования `DEBUG_NEW`, вставьте следующую директиву в исходные файлы:  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 После добавления этой директивы препроцессора вставит `DEBUG_NEW` везде, где используется **новый**, а MFC сделает все остальное. При компиляции окончательной версии программы, `DEBUG_NEW` становится простой **новый** операции и имя файла сведения и номере строки не создаются.  
  
> [!NOTE]
>  В предыдущих версиях MFC (4.1 и более ранних версий) необходимо поместить `#define` инструкции после всех инструкций, которые вызваны `IMPLEMENT_DYNCREATE` или `IMPLEMENT_SERIAL` макросы. Это не требуется.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-namedebugonlya--debugonly"></a><a name="debug_only"></a>DEBUG_ONLY  
 В режиме отладки (когда **_DEBUG** символ определен), `DEBUG_ONLY` проверяет его аргумент.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>Примечания  
 В окончательном построении **DEBUG_ONLY** не оценивает своего аргумента. Это полезно в том случае, если у вас есть код, который должен быть выполнен только в отладочных сборках.  
  
 `DEBUG_ONLY` Макрос равнозначен вокруг *выражение* с **#ifdef _DEBUG** и `#endif`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#32;](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-nametracea--trace"></a><a name="trace"></a>ТРАССИРОВКИ  
 Отправляет указанную строку в отладчике текущего приложения.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ATLTRACE2](http://msdn.microsoft.com/library/467ff555-e7a5-4f94-bdd9-50ee27ab9986) описание **ТРАССИРОВКИ**. **ТРАССИРОВКИ** и `ATLTRACE2` имеют одинаковое поведение.  
  
 В отладочной версии MFC этот макрос отправляет указанную строку текущего приложения в отладчике. В сборке выпуска этот макрос компилируется nothing (код не создается вообще).  
  
 Дополнительные сведения см. в разделе [отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-nameverifya--verify"></a><a name="verify"></a>ПРОВЕРКА  
 В отладочной версии MFC проверяет его аргумент.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Указывает выражение (включая значения указателя), результатом которого является нуля или равен нулю.  
  
### <a name="remarks"></a>Примечания  
 Если результат равен 0, макрос выводит диагностическое сообщение и останавливает выполнение программы. Если условие имеет ненулевое значение, он не выполняет никаких действий.  
  
 Диагностическое сообщение имеет форму  
  
 `assertion failed in file <name> in line <num>`  
  
 где *имя* — имя исходного файла и *num* — это номер строки утверждения, сбой в исходном файле.  
  
 В окончательной версии MFC **ПРОВЕРИТЬ** вычисляет выражение, но не печатать или прерывания работы программы. Например если выражение является вызовом функции, будет выполнен вызов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#198;](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-namecdumpcontextinmfca--afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc_"></a>afxDump (CDumpContext в MFC)  
 Предоставляет основные возможности формирование дампа объекта в приложении.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>Примечания  
 `afxDump`стандартный [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объект, который можно отправить `CDumpContext` сведений в окне вывода или терминалов отладки. Как правило, необходимо указать `afxDump` в качестве параметра `CObject::Dump`.  
  
 В Windows NT и всех версиях Windows `afxDump` выходные данные направляются в окно вывода отладки Visual C++ при отладке приложения.  
  
 Эта переменная определяется только в отладочной версии MFC. Дополнительные сведения о `afxDump`, в разделе [отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#23;](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-nameafxmemdfa--afxmemdf"></a><a name="afxmemdf"></a>afxMemDF  
 Эта переменная доступна из отладчика или программы и позволяет настраивать диагностики выделения.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>Примечания  
 `afxMemDF`может иметь следующие значения, заданные в перечислении `afxMemDF`:  
  
- **allocMemDF** Включение отладки распределителя (по умолчанию в отладочной библиотеке).  
  
- **delayFreeMemDF** задерживает освобождение памяти. Хотя программа освобождает блок памяти, распределитель возвращает памяти операционной системы. Это будет помещен нагрузки максимальный объем памяти в программе.  
  
- **checkAlwaysMemDF** вызовов `AfxCheckMemory` каждый раз при выделении или освобождении памяти. Это значительно снижает скорость выделения памяти и освобождения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#30;](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-nameafxcheckerrora--afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheckError  
 Эта функция проверяет переданный **SCODE** ли ошибка.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>Примечания  
 Если это ошибка, функция создает исключение. Если переданный `SCODE` — **E_OUTOFMEMORY**, функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md) путем вызова [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). В противном случае, функция создает [COleException](../../mfc/reference/coleexception-class.md) путем вызова [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Эту функцию можно использовать для проверки возвращаемых значений вызовов функции OLE в приложении. Тестирование возвращаемое значение с помощью этой функции в приложении, может правильно реагировать на ошибки с минимальным объемом кода.  
  
> [!NOTE]
>  Эта функция действует так же, в режиме отладки и построения без отладки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#33;](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h

##  <a name="a-nameafxcheckmemorya--afxcheckmemory"></a><a name="afxcheckmemory"></a>AfxCheckMemory  
 Эта функция проверяет в пул свободной памяти и выводит сообщения об ошибках при необходимости.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если ошибки памяти; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если функция обнаруживает повреждение памяти, он выводит ничего.  
  
 Проверяются все блоки памяти, выделенной в данный момент в куче, включая те, выделяемая **новый** , а не те, которые выделены прямые вызовы базовых механизмов выделения памяти, таких как `malloc` функции или **GlobalAlloc** функции Windows. Найденный любой блок поврежден сообщение выводится в выходные данные отладчика.  
  
 Если включить строку  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 в модуле программы, то последующие вызовы `AfxCheckMemory` Показать файла и номер строки, где была выделена память.  
  
> [!NOTE]
>  Если модуль содержит один или несколько реализаций сериализуемых классов, то необходимо поместить `#define` строки после последнего `IMPLEMENT_SERIAL` вызов макроса.  
  
 Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&#26;](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
 
##  <a name="a-namemfca--afxdump-mfc"></a><a name="mfc_"></a>AfxDump (MFC)  
 Вызов этой функции в отладчике в дамп состояние объекта во время отладки.  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>Параметры  
 `pOb`  
 Указатель на объект класса, производный от `CObject`.  
  
### <a name="remarks"></a>Примечания  
 **AfxDump** вызывает объект `Dump` функция-член и отправляет данные в расположение, определяемое `afxDump` переменной. **AfxDump** доступна только в отладочной версии MFC.  
  
 Программный код не должен вызывать **AfxDump**, но вместо этого следует вызывать `Dump` функции-члена объекта.  
  
##  <a name="a-nameafxdumpstacka--afxdumpstack"></a><a name="afxdumpstack"></a>AfxDumpStack  
 Эту глобальную функцию можно использовать для создания изображения текущего стека.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>Параметры  
 *dwTarget*  
 Указывает целевой выходные данные дампа. Возможные значения, которые можно комбинировать с помощью побитового или ( **|**) оператор, таковы:  
  
- **AFX_STACK_DUMP_TARGET_TRACE** отправляет выходные данные с помощью параметра [ТРАССИРОВКИ](#trace) макрос. **ТРАССИРОВКИ** макрос создает выходные данные в только в отладочных построениях; он не создает выходные данные в сборке выпуска. Кроме того **ТРАССИРОВКИ** может быть перенаправлен на других целевых объектов, кроме отладчик.  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT** дампа отправляет выходные данные целевого объекта по умолчанию. Для отладочной сборки, результат выводится в **ТРАССИРОВКИ** макрос. В сборке выпуска результат выводится в буфер обмена.  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD** отправляет выходные данные только в буфер обмена. Данные помещаются в буфер обмена как обычный текст с помощью **CF_TEXT** формат буфера обмена.  
  
- **AFX_STACK_DUMP_TARGET_BOTH** отправляет выходные данные в буфер обмена и **ТРАССИРОВКИ** макрос, одновременно.  
  
- **AFX_STACK_DUMP_TARGET_ODS** отправляет выходные данные непосредственно в отладчик с помощью функции Win32 **OutputDebugString()**. Этот параметр будет вывод в отладчик в обоих отладки и построения выпуска, если отладчик присоединен к процессу. **AFX_STACK_DUMP_TARGET_ODS** всегда достигает отладчика (если он подключен) и не может быть перенаправлен.  
  
### <a name="remarks"></a>Примечания  
 В приведенном ниже примере отражает одной строки выходных данных, полученных из вызова метода `AfxDumpStack` из обработчика кнопки в диалоговом окне приложения MFC:  
  
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
  
 Каждая строка в приведенном выше примере адрес последнего вызова функции, полное имя модуля, содержащего вызов функции и вызывается прототип функции. Если вызов функции в стеке происходит не на адрес функции, отображается смещение байтов.  
  
 Например в следующей таблице описаны первой строки приведенных выше выходных данных:  
  
|Вывод|Описание|  
|------------|-----------------|  
|`00427D55:`|Обратный адрес последнего вызова функции.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|Полный путь к модулю, содержащему вызов функции.|  
|`void AfxDumpStack(unsigned long)`|Прототип функции вызывается.|  
|`+ 181 bytes`|Смещение в байтах от адреса прототип функции (в данном случае `void AfxDumpStack(unsigned long)`) на обратный адрес (в данном случае `00427D55`).|  
  
 `AfxDumpStack`доступно в версиях отладки и отладки библиотек MFC; Однако функция всегда связан статически, даже в том случае, если исполняемый файл использует MFC в общей библиотеке DLL. Функция находится в MFCS42 реализации общей библиотеки. Библиотека LIB (и его разновидностей).  
  
 Для успешного использования этой функции:  
  
-   Файл IMAGEHLP. Библиотеки DLL должны находиться в пути. Если у вас этой библиотеки DLL, функция отобразит сообщение об ошибке. В разделе [образа библиотеки справки](http://msdn.microsoft.com/library/windows/desktop/ms680321) сведения о набор функций, предоставляемых IMAGEHLP.  
  
-   Модули, которые имеют кадров в стеке должны включать отладочную информацию. Если они не содержат сведения об отладке, функция будет по-прежнему создавать трассировку стека, но трассировка будет менее подробным.  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxenablememoryleakdumpa--afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump  
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
 Когда приложение выгружает библиотеку MFC, она выполняет проверку на наличие утечек памяти. На этом этапе любой утечки памяти выводятся пользователю через **отладки** окно [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Если приложение загружает другую библиотеку перед библиотекой MFC, некоторые выделения памяти в этой библиотеке ошибочно выводятся как утечки памяти. Ложные утечки памяти могут привести к медленному закрытию приложения, пока библиотека MFC сообщает о них. В этом случае воспользуйтесь `AfxEnableMemoryLeakDump` , чтобы отключить дамп утечки памяти.  
  
> [!NOTE]
>  При использовании этого метода для отключения дампа утечки памяти вы не будете получать отчеты о действительных утечках памяти в приложении. Этот метод следует использовать только в том случае, если вы уверены, что в отчете представлены только ложные утечки памяти.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxenablememorytrackinga--afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnableMemoryTracking  
 Отслеживание диагностики памяти обычно включена в отладочной версии MFC.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>Параметры  
 *bTrack*  
 Установка этого значения в **TRUE** включает памяти; **FALSE** отключает его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущего параметра флаг включения отслеживания.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для отключения трассировки в разделах, вы знаете правильно выделения блоков кода.  
  
 Дополнительные сведения о `AfxEnableMemoryTracking`, в разделе [отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#24;](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxismemoryblocka--afxismemoryblock"></a><a name="afxismemoryblock"></a>AfxIsMemoryBlock  
 Проверяет адрес памяти, чтобы убедиться, что он представляет блок активной памяти, который был выделен диагностики версии **новый**.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на блок памяти для тестирования.  
  
 `nBytes`  
 Содержит длину блока памяти в байтах.  
  
 `plRequestNumber`  
 Указывает **длинные** целое число, которое будет заполнено порядковый номер выделения блока памяти, или нуль, если не представляет блок активной памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если блок памяти в настоящее время выделяется и длина правильно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Он также проверяет от исходного размера, выделенного указанного размера. Если функция возвращает ненулевое значение, порядковый номер выделения возвращается в `plRequestNumber`. Это число представляет порядок, в котором был выделен блок относительно всех других **новый** выделения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#27;](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxisvalidaddressa--afxisvalidaddress"></a><a name="afxisvalidaddress"></a>AfxIsValidAddress  
 Проверяет, любой адрес памяти, чтобы содержится целиком в пределах пространства памяти программы.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>Параметры  
 `lp`  
 Указывает адрес памяти для тестирования.  
  
 `nBytes`  
 Содержит количество байт памяти для тестирования.  
  
 *bReadWrite*  
 Указывает, является ли память как для чтения и записи ( **TRUE**) или только чтение ( **FALSE**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях ненулевое значение, если блок памяти указанного содержится полностью в пространстве памяти программы; в противном случае — 0.  
  
 В неотладочных сборках отличное от нуля значение `lp` не равно NULL; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Адрес не ограничивается блоки выделенные **новый**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#28;](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxisvalidstringa--afxisvalidstring"></a><a name="afxisvalidstring"></a>AfxIsValidString  
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
 Указывает длину строки, которое необходимо проверить, в байтах. Значение из â €«1 показывает, что строка символом null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях, ненулевое значение, если заданный указатель указывает на строку указанного размера; в противном случае — 0.  
  
 В неотладочных сборках отличное от нуля значение `lpsz` не равно NULL; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#29;](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxsetallochooka--afxsetallochook"></a><a name="afxsetallochook"></a>AfxSetAllocHook  
 Задает обработчик, который включает вызов указанной функции до распределения каждого блока памяти.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>Параметры  
 *pfnAllocHook*  
 Задает имя функции. См. заметки для прототипа функции выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если необходимо разрешить распределения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Механизм распределения отладочной памяти библиотеки классов Microsoft Foundation можно вызвать функция-ловушка пользовательские разрешения пользователю для отслеживания выделения памяти и управления, разрешено ли выделение. Прототипы функций-ловушек выделения следующим образом:  
  
 **BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**  
  
 `nSize`  
 Размер выделения памяти предложенный.  
  
 `bObject`  
 **Значение TRUE,** если выделение находится для `CObject`-производный объект; в противном случае **FALSE**.  
  
 `lRequestNumber`  
 Порядковый номер выделения памяти.  
  
 Обратите внимание, что **AFXAPI** соглашение о вызовах означает, что вызываемый объект необходимо удалить параметры из стека.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxdoforallclassesa--afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxDoForAllClasses  
 Вызывает функцию определенной итерации для всех сериализуемых `CObject`-производные классы в пространстве памяти приложения.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Параметры  
 `pfn`  
 Указывает на итерацию функция, вызываемая для каждого класса. Аргументы функции не указатель на `CRuntimeClass` объект и указатель void дополнительные данные, которые вызывающий объект передает в функцию.  
  
 `pContext`  
 Указывает дополнительные данные, которые вызывающий объект может предоставить функцию итерации. Этот указатель может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Сериализуемый `CObject`-производные классы являются классы, производные с использованием `DECLARE_SERIAL` макрос. Указатель, передаваемый `AfxDoForAllClasses` в `pContext` передается функции определенной итерации при каждом вызове.  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#113;](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&#114;](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameafxdoforallobjectsa--afxdoforallobjects"></a><a name="afxdoforallobjects"></a>AfxDoForAllObjects  
 Выполняет функцию определенной итерации для всех объектов, производных от `CObject` была выделена с **новый**.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Параметры  
 `pfn`  
 Указывает функцию итерации для выполнения для каждого объекта. Аргументы функции не указатель на `CObject` и указатель void дополнительные данные, которые вызывающий объект передает в функцию.  
  
 `pContext`  
 Указывает дополнительные данные, которые вызывающий объект может предоставить функцию итерации. Этот указатель может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Стек, глобальная или внедренные объекты, не перечисляются. Указатель, переданный в `AfxDoForAllObjects` в `pContext` передается функции определенной итерации при каждом вызове.  
  
> [!NOTE]
>  Эта функция работает только в отладочной версии MFC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#115;](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&116;](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
