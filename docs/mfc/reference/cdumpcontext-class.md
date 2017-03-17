---
title: "Класс CDumpContext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext class
- AfxDump object
- diagnostics, diagnostic classes
- diagnostic classes
- diagnosis, diagnostic classes
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 40d833772735e1079647f8f3205fb8db736843fd
ms.lasthandoff: 02/24/2017

---
# <a name="cdumpcontext-class"></a>Класс CDumpContext
Поддерживает ориентированных на поток диагностические данные в форме человекочитаемого текста.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|Создает объект `CDumpContext`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|Создает дамп указанного элемента в шестнадцатеричном формате.|  
|[CDumpContext::Flush](#flush)|Очищает все данные в буфере контекста дампа.|  
|[CDumpContext::GetDepth](#getdepth)|Возвращает целое число, соответствующее глубине дампа.|  
|[CDumpContext::HexDump](#hexdump)|Создает дамп байтов, содержащихся в массиве в шестнадцатеричном формате.|  
|[CDumpContext::SetDepth](#setdepth)|Задает глубину дампа.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDumpContext::operator&lt;&lt;](#operator_lt_lt)|Вставляет переменные и объекты в контекст дампа.|  
  
## <a name="remarks"></a>Примечания  
 `CDumpContext`не имеет базового класса.  
  
 Можно использовать [afxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11), predeclared `CDumpContext` объекта, для большинства вашей формирование дампа. `afxDump` Объект доступен только в отладочной версии библиотеки классов Microsoft Foundation.  
  
 Некоторые из памяти [диагностические службы](../../mfc/reference/diagnostic-services.md) использовать `afxDump` для свои выходные данные.  
  
 В среде Windows, выходные данные из предварительно определенных `afxDump` объекта, концептуально сходная с `cerr` потока, направляется в отладчике через функцию Windows **OutputDebugString**.  
  
 `CDumpContext` Класс имеет перегруженные Вставка ( ** << **) оператор для `CObject` указатели, которые создает дамп данных объекта. Если вам требуется формат пользовательского дампа для производного объекта, переопределяют [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Большинство классов Microsoft Foundation реализуют переопределенный `Dump` функции-члена.  
  
 Классы, которые не являются производными от `CObject`, такие как `CString`, `CTime`, и `CTimeSpan`, имеют свои собственные перегруженных `CDumpContext` операторы вставки, как часто используется структуры, таких как **CFileStatus**, `CPoint`, и `CRect`.  
  
 При использовании [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) или [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос в реализации класса, затем `CObject::Dump` выводит имя вашего `CObject`-производного класса. В противном случае, напечатает `CObject`.  
  
 `CDumpContext` Класс доступен с отладочной и окончательной версии библиотеки, но `Dump` функция-член определяется только в отладочной версии. Используйте **#ifdef _DEBUG**  /  `#endif` скобкой код диагностики, включая пользовательских инструкций `Dump` функции-члены.  
  
 Прежде чем создавать собственные `CDumpContext` объекта, необходимо создать `CFile` объект, выступающий в качестве назначения дампа.  
  
 Дополнительные сведения о `CDumpContext`, в разделе [отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
 **#define _DEBUG**  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDumpContext`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cdumpcontext"></a>CDumpContext::CDumpContext  
 Создает объект класса `CDumpContext`.  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pFile`  
 Указатель на `CFile` объект, который является конечным дампа.  
  
### <a name="remarks"></a>Примечания  
 `afxDump` Объект будет создан автоматически.  
  
 Не записывать в базовом `CFile` при активна; в противном случае контекст дампа будет мешать дампа. В среде Windows вывод направляется в отладчик через функцию Windows **OutputDebugString**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#12;](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>CDumpContext::DumpAsHex  
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
 Вызов этой функции-члена для дампа элемент указанного типа в шестнадцатеричном формате. Для помещения в дамп массив, вызовите [CDumpContext::HexDump](#hexdump).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#13;](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>CDumpContext::Flush  
 Заставляет все данные в буферах, в файл присоединен к контексту дампа.  
  
```  
void Flush();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#14;](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>CDumpContext::GetDepth  
 Определяет, является ли процесс глубоко или поверхностно дампа.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Глубина дампа, заданного методом `SetDepth`.  
  
### <a name="example"></a>Пример  
  В примере показано [SetDepth](#setdepth).  
  
##  <a name="hexdump"></a>CDumpContext::HexDump  
 Выводит массив байтов в формате шестнадцатеричных чисел.  
  
```  
void HexDump(
    LPCTSTR lpszLine,  
    BYTE* pby,  
    int nBytes,  
    int nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszLine*  
 Строка для вывода в начале новой строки.  
  
 *pby*  
 Указатель на буфер, содержащий в байтах.  
  
 `nBytes`  
 Число байтов для помещения в дамп.  
  
 `nWidth`  
 Максимальное число байтов, записаны в строке (не ширина строки выхода).  
  
### <a name="remarks"></a>Примечания  
 Для вывода типа отдельной элемента в шестнадцатеричном формате, вызовите [CDumpContext::DumpAsHex](#dumpashex).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#15;](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="operator_lt_lt"></a>CDumpContext::operator&lt;&lt;  
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
 A `CDumpContext` ссылки. Возвращаемое значение можно написать несколько операций вставки в одной строке исходного кода.  
  
### <a name="remarks"></a>Примечания  
 Для перегрузки оператора вставки `CObject` также как и большинство примитивных типов указателей. Указатель на символ результаты в дамп содержимого строки; указатель на `void` результатов в шестнадцатеричном дампе только адреса. Объект **longlong ПРИВЕДЕННЫМ** результатов в дамп 64-разрядное знаковое целое число; Объект **ULONGLONG** выводится дамп 64-разрядного целого числа без знака.  
  
 При использовании `IMPLEMENT_DYNAMIC` или `IMPLEMENT_SERIAL` макрос в реализации класса, а затем оператор вставки через `CObject::Dump`, напечатает имя вашего `CObject`-производного класса. В противном случае, напечатает `CObject`. При переопределении `Dump` функции класса, то можно предоставить более осмысленными вывод содержимого объекта вместо шестнадцатеричных дампа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&17;](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>CDumpContext::SetDepth  
 Задает глубину для дампа.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>Параметры  
 *nNewDepth*  
 Новое значение глубины.  
  
### <a name="remarks"></a>Примечания  
 Если выполняется дамп является простым типом или простой `CObject` , не содержит указателей на другие объекты, то достаточно значение 0. Значение больше 0 задает глубокой дампа, когда все объекты были записаны рекурсивно. Например сложного дамп коллекции выгружать все элементы коллекции. Вы можете использовать другие значения определенных глубины в производных классах.  
  
> [!NOTE]
>  Циклические ссылки не обнаруживаются в глубокой дампы и может привести к бесконечных циклов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities №&16;](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)

