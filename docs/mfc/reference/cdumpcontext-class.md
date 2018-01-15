---
title: "Класс CDumpContext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d54a461bece96faeb11f78a1788049abcabbae0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|[CDumpContext::Flush](#flush)|Очищает все данные в буфере контекста дампа.|  
|[CDumpContext::GetDepth](#getdepth)|Возвращает целое число, соответствующее глубину дампа.|  
|[CDumpContext::HexDump](#hexdump)|Выводит байтов, содержащихся в массиве в шестнадцатеричном формате.|  
|[CDumpContext::SetDepth](#setdepth)|Задает глубину дампа.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDumpContext::operator&lt;&lt;](#operator_lt_lt)|Вставляет переменные и объекты в контекст дампа.|  
  
## <a name="remarks"></a>Примечания  
 `CDumpContext`не имеет базового класса.  
  
 Можно использовать [afxDump](diagnostic-services.md#afxdump), объявленная ранее `CDumpContext` объекта, для большинства вашей формирование дампа. `afxDump` Объект доступен только в отладочной версии библиотеки классов Microsoft Foundation.  
  
 Некоторые из памяти [службы диагностики](../../mfc/reference/diagnostic-services.md) использовать `afxDump` для свои выходные данные.  
  
 В среде Windows, выходные данные о стандартных `afxDump` объекта, по существу аналогично `cerr` потока, направляется в отладчике через функцию Windows **OutputDebugString**.  
  
 `CDumpContext` Класс имеет перегруженные Вставка (  **<<** ) оператор для `CObject` указателей, которые создает дамп данных объекта. Если вам требуется формат дампа пользовательского производного объекта, переопределяют [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Большинство классов Microsoft Foundation реализуют переопределенный `Dump` функции-члена.  
  
 Классы, которые не являются производными от `CObject`, такие как `CString`, `CTime`, и `CTimeSpan`, имеют собственные перегруженных `CDumpContext` операторы вставки, как часто используется структуры, такие как **CFileStatus**, `CPoint`, и `CRect`.  
  
 При использовании [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) или [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос в реализации класса, затем `CObject::Dump` напечатает имя вашей `CObject`-производного класса. В противном случае оно печатается `CObject`.  
  
 `CDumpContext` Класс доступен с отладочной и окончательной версии библиотеки, но `Dump` функция-член определяется только в отладочной версии. Используйте **#ifdef _DEBUG**  /  `#endif` инструкции, чтобы квадратная скобка диагностики кода, включая пользовательскую `Dump` функции-члены.  
  
 Прежде чем создавать собственные `CDumpContext` объекта, необходимо создать `CFile` объект, который служит в качестве назначения дампа.  
  
 Дополнительные сведения о `CDumpContext`, в разделе [отладки приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
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
 Указатель на `CFile` объект, который является целевым дампа.  
  
### <a name="remarks"></a>Примечания  
 `afxDump` Объект будет создан автоматически.  
  
 Не выполняйте запись в базовый `CFile` при активен; в противном случае контекст дампа будет мешать дампа. В среде Windows вывод направляется в отладчике через функцию Windows **OutputDebugString**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>CDumpContext::DumpAsHex  
 Выводит указанного типа, представленного шестнадцатеричных чисел.  
  
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
 Вызовите эту функцию-член для помещения в дамп элемент заданного типа, как шестнадцатеричное число. Для помещения в дамп массив вызвать [CDumpContext::HexDump](#hexdump).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>CDumpContext::Flush  
 Заставляет все данные, оставшиеся в буферах, в файл присоединен к контексту дампа.  
  
```  
void Flush();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>CDumpContext::GetDepth  
 Определяет, является ли глубоко или поверхностно дамп процесса.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Глубина дампа, задаваемое при помощи `SetDepth`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [SetDepth](#setdepth).  
  
##  <a name="hexdump"></a>CDumpContext::HexDump  
 Выводит массив байтов, в формате шестнадцатеричных чисел.  
  
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
 Указатель на буфер, содержащий байты для помещения в дамп.  
  
 `nBytes`  
 Число байтов для помещения в дамп.  
  
 `nWidth`  
 Максимальное число байтов записаны в каждой строке (не толщину линии выходных данных).  
  
### <a name="remarks"></a>Примечания  
 Для помещения в дамп типа конкретную элемента как шестнадцатеричное число, вызовите [CDumpContext::DumpAsHex](#dumpashex).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
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
 Объект `CDumpContext` ссылки. Возвращаемое значение можно написать несколько операций вставки в одной строке исходного кода.  
  
### <a name="remarks"></a>Примечания  
 Оператор вставки перегружается для `CObject` указатели также, как и большинство примитивных типов. Указатель на символ результаты в дамп содержимого строки; указатель на `void` результатов в шестнадцатеричном дампе только адреса. Объект **longlong ПРИВЕДЕННЫМ** выводится дамп 64-разрядного целого числа со знаком; Объект **ULONGLONG** выводится дамп 64-разрядного целого числа без знака.  
  
 При использовании `IMPLEMENT_DYNAMIC` или `IMPLEMENT_SERIAL` макрос в реализации класса, а затем оператор вставки через `CObject::Dump`, будет печататься имя вашей `CObject`-производного класса. В противном случае оно печатается `CObject`. При переопределении `Dump` функции класса, то можно провести более понятные выходные данные из содержимого этого объекта вместо шестнадцатеричный дамп.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>CDumpContext::SetDepth  
 Задает глубину для дампа.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>Параметры  
 *nNewDepth*  
 Новое значение глубины.  
  
### <a name="remarks"></a>Примечания  
 Если формирование дампа типом-примитивом или простой `CObject` , не содержит указателей на другие объекты, то достаточно значение 0. Значение больше 0 задает глубокой дампа, когда все объекты были записаны рекурсивно. Например сложного дампа коллекции будет дампа все элементы коллекции. В производных классах, могут использоваться другие значения определенной глубины.  
  
> [!NOTE]
>  Циклические ссылки не определяются в глубоких дампы и может привести к бесконечные циклы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
