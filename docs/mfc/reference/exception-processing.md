---
title: "Обработка исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros, exception handling
- DAO (Data Access Objects), exceptions
- OLE exceptions, MFC functions
- exceptions, processing
- exception macros
- termination functions, MFC
- MFC, exceptions
- exceptions, MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
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
ms.openlocfilehash: a2ded9c49a9f6935a5b268ccbefc4678af184029
ms.lasthandoff: 02/24/2017

---
# <a name="exception-processing"></a>Обработка исключений
При выполнении программы, может возникнуть ряд нештатных ситуаций и ошибок, называется «исключения». Они могут включать нехватки памяти, ошибки выделения ресурсов и не удалось найти файлы.  
  
 Библиотеки классов Microsoft Foundation использует схему обработки исключений, моделируется точно один комитета по стандартам ANSI, рекомендованные для C++. Обработчик исключений необходимо настроить, прежде чем вызов функции, могут возникнуть нестандартной ситуации. Если функция обнаруживает чрезмерное условие, создается исключение, и управление передается обработчику исключений.  
  
 Несколько макросов, входящий в состав библиотеки классов Microsoft Foundation устанавливаются обработчики исключений. Ряд других глобальные функции помогают создавать специальные исключения и завершение программы, при необходимости. Эти макросы и глобальные функции делятся на следующие категории:  
  
- Макросы исключений, которые структура обработчика исключений.  
  
- Exception-throwing функции), которые создают исключения определенных типов.  
  
- Функции завершения, которые вызывают завершение программы.  
  
 Примеры и Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="exception-macros"></a>Макросы исключений  
  
|||  
|-|-|  
|[ПОПРОБУЙТЕ](#try)|Определяет блок кода для обработки исключений.|  
|[CATCH](#catch)|Определяет блок кода для перехвата исключения из предыдущих **попробуйте** блок.|  
|[CATCH_ALL](#catch_all)|Определяет блок кода для перехвата всех исключений из предыдущих **попробуйте** блок.|  
|[AND_CATCH](#and_catch)|Определяет блок кода для перехвата исключений дополнительные типы из предыдущих **попробуйте** блок.|  
|[AND_CATCH_ALL](#and_catch_all)|Определяет блок кода для перехвата всех других типов дополнительные исключения, исключение в предыдущих **попробуйте** блок.|  
|[END_CATCH](#end_catch)|Завершает последний **CATCH** или `AND_CATCH` блок кода.|  
|[END_CATCH_ALL](#end_catch_all)|Завершает последний `CATCH_ALL` блок кода.|  
|[THROW](#throw)|Создает указанное исключение.|  
|[THROW_LAST](#throw_last)|В настоящее время обработки исключения в обработчик следующий внешний.|  
  
### <a name="exception-throwing-functions"></a>Функции, создающие исключения  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Исключение архива.|  
|[AfxThrowFileException](#afxthrowfileexception)|Исключение файла.|  
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Исключение памяти.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Исключение не поддерживается.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Исключение Windows ресурс не найден.|  
|[AfxThrowUserException](#afxthrowuserexception)|Исключение в действии пользователь запустил программу.|  
  
 MFC предоставляет две функции, создающие исключения специально для OLE-исключения:  
  
### <a name="ole-exception-functions"></a>Функции исключения OLE  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Создает исключение внутри функции автоматизации OLE.|  
|[AfxThrowOleException](#afxthrowoleexception)|Исключение OLE.|  
  
 Для поддержки исключения базы данных, классы базы данных предоставляют два класса исключения `CDBException` и `CDaoException`и глобальные функции для поддержки типов исключений:  
  
### <a name="dao-exception-functions"></a>Функции исключения DAO  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Создает [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.|  
|[AfxThrowDBException](#afxthrowdbexception)|Создает [CDBException](../../mfc/reference/cdbexception-class.md) из собственного кода.|  
  
 MFC предоставляет следующие функции завершения:  
  
### <a name="termination-functions"></a>Функции завершения  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|Вызывается для завершения приложения при Неустранимая ошибка возникает.|  
  
##  <a name="a-nametrya--try"></a><a name="try"></a>ПОПРОБУЙТЕ  
 Настраивает **попробуйте** блок.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>Примечания  
 Объект **попробуйте** блок определяет блок кода, который может создавать исключения. Эти исключения обрабатываются в следующем **CATCH** и `AND_CATCH` блоков. Рекурсия разрешена: исключения могут быть переданы внешнем **попробуйте** блока, пропуская их или используя `THROW_LAST` макрос. Конец **попробуйте** блок с `END_CATCH` или `END_CATCH_ALL` макрос.  
  
 Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 В примере показано [CATCH](#catch).  

### <a name="requirements"></a>Требования
Заголовок: afx.h

##  <a name="a-namecatcha--catch"></a><a name="catch"></a>CATCH  
 Определяет блок кода, который перехватывает исключение в предыдущем примере первый тип исключения **попробуйте** блок.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>Параметры  
 *exception_class*  
 Указывает тип исключения для тестирования. Список исключений стандартных классов, см. [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Указывает имя для указателя на объект исключения, будет создан при помощи макроса. Имя указателя можно использовать для доступа к объекту исключения в **CATCH** блок. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызов `THROW_LAST` макрос для сдвига обработки на следующий кадр внешнее исключение. Конец **попробуйте** блок с `END_CATCH` макрос.  
  
 Если *exception_class* — это класс `CException`, а затем все типы исключение будет перехвачено. Можно использовать [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) функции-члена для определения, какие конкретного исключения. Для перехвата несколько типов исключений, лучше использовать последовательный `AND_CATCH` инструкций, каждый из которых имеет другой тип исключения.  
  
 Указатель на объект исключения создается макросом. Необходимо объявить ее.  
  
> [!NOTE]
>  **CATCH** блока определяется как C++ области, разделенное фигурными скобками. При объявлении переменных в этой области, они доступны только внутри этой области. Это также относится к *exception_object_pointer_name*.  
  
 Дополнительные сведения об исключениях и **CATCH** макрос, см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCExceptions&#26;](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="a-namecatchalla--catchall"></a><a name="catch_all"></a>CATCH_ALL  
 Определяет блок кода, который перехватывает все типы исключений, исключение в предыдущем **попробуйте** блок.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *exception_object_pointer_name*  
 Указывает имя для указателя на объект исключения, будет создан при помощи макроса. Имя указателя можно использовать для доступа к объекту исключения в `CATCH_ALL` блок. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызов `THROW_LAST` макрос для сдвига обработки на следующий кадр внешнее исключение. При использовании `CATCH_ALL`, конец **попробуйте** блок с `END_CATCH_ALL` макрос.  
  
> [!NOTE]
>  `CATCH_ALL` Блока определяется как C++ области, разделенное фигурными скобками. При объявлении переменных в этой области, они доступны только внутри этой области.  
  
 Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 В примере показано [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  

##  <a name="a-nameandcatcha--andcatch"></a><a name="and_catch"></a>AND_CATCH  
 Определяет блок кода для перехвата типа дополнительных исключений, исключение в предыдущих **попробуйте** блок.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *exception_class*  
 Указывает тип исключения для тестирования. Список исключений стандартных классов, см. [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Имя для указателя на объект исключения, будет создан при помощи макроса. Имя указателя можно использовать для доступа к объекту исключения в `AND_CATCH` блок. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Используйте **CATCH** макрос для перехвата один тип исключения, то `AND_CATCH` макрос для каждого последующего типа. Конец **попробуйте** блок с `END_CATCH` макрос.  
  
 Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызов `THROW_LAST` макрос в `AND_CATCH` блока обработки на следующий кадр внешнее исключение shift. `AND_CATCH`отмечает конец предыдущего **CATCH** или `AND_CATCH` блока.  
  
> [!NOTE]
>  `AND_CATCH` Блок представляет собой область C++ (разделенные символами фигурные скобки). При объявлении переменных в этой области, помните, что они доступны только внутри этой области. Это также относится к *exception_object_pointer_name* переменной.  
  
### <a name="example"></a>Пример  
 В примере показано [CATCH](#catch).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
##  <a name="a-nameandcatchalla--andcatchall"></a><a name="and_catch_all"></a>AND_CATCH_ALL  
 Определяет блок кода для перехвата типа дополнительных исключений, исключение в предыдущих **попробуйте** блок.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>Параметры  
 *exception_object_pointer_name*  
 Имя для указателя на объект исключения, будет создан при помощи макроса. Имя указателя можно использовать для доступа к объекту исключения в `AND_CATCH_ALL` блок. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Используйте **CATCH** макрос для перехвата один тип исключения, то `AND_CATCH_ALL` макрос для перехвата всех других типов последующие. При использовании `AND_CATCH_ALL`, конец **попробуйте** блок с `END_CATCH_ALL` макрос.  
  
 Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызов `THROW_LAST` макрос в `AND_CATCH_ALL` блока обработки на следующий кадр внешнее исключение shift. `AND_CATCH_ALL`отмечает конец предыдущего **CATCH** или `AND_CATCH_ALL` блока.  
  
> [!NOTE]
>  `AND_CATCH_ALL` Блок представляет собой область C++ (разделенные символами фигурные скобки). При объявлении переменных в этой области, помните, что они доступны только внутри этой области.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameendcatcha--endcatch"></a><a name="end_catch"></a>END_CATCH  
 Отмечает конец последнего **CATCH** или `AND_CATCH` блока.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о `END_CATCH` макрос, см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameendcatchalla--endcatchall"></a><a name="end_catch_all"></a>END_CATCH_ALL  
 Отмечает конец последнего `CATCH_ALL` или `AND_CATCH_ALL` блока.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-namethrowa--throw-mfc"></a><a name="throw"></a>THROW (MFC)  
 Создает указанное исключение.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>Параметры  
 *exception_object_pointer*  
 Указывает на объект исключения производным от `CException`.  
  
### <a name="remarks"></a>Примечания  
 **ИСКЛЮЧЕНИЕ** прерывания выполнения, передать управление соответствующим программы **CATCH** блокировки в приложении. Если вы не указали **CATCH** заблокировать, а затем управление передается модуль библиотеки Microsoft Foundation Class, который выводит ошибку, сообщение и завершает работу.  
  
 Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-namethrowlasta--throwlast"></a><a name="throw_last"></a>THROW_LAST  
 Создает исключение обратно к следующему внешнего **CATCH** блок.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>Примечания  
 Этот макрос позволяет локально созданного исключения. При попытке создать исключение только привлек, он обычно выйдут из области действия и удаляться. С `THROW_LAST`, исключение передается правильно к следующему **CATCH** обработчика.  
  
 Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 В примере показано [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowarchiveexceptiona--afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 Исключение архива.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>Параметры  
 `cause`  
 Указывает целое число, указывающее причину возникновения исключения. Список возможных значений см. в разделе [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).  
  
 `lpszArchiveName`  
 Указывает строку, содержащую имя `CArchive` объекта, вызвавшего исключение (если доступно).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowfileexceptiona--afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileException  
 Исключение файла.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `cause`  
 Указывает целое число, указывающее причину возникновения исключения. Список возможных значений см. в разделе [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).  
  
 `lOsError`  
 Содержит номер ошибки операционной системы (если доступно), указывающее причину возникновения исключения. См. список кодов ошибок операционной системы вручную.  
  
 `lpszFileName`  
 Указывает строку, содержащую имя файла, вызвавшего исключение (если доступно).  
  
### <a name="remarks"></a>Примечания  
 Вы несете ответственность за определение причины, на основе кода ошибки операционной системы.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowmemoryexceptiona--afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 Исключение памяти.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, если вызовы базовых механизмов выделения памяти системы (например, `malloc` и [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) функции Windows) ошибкой. Не нужно вызывать его для **новый** из-за **новый** выдаст исключение памяти автоматически, если происходит сбой выделения памяти.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrownotsupportedexceptiona--afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 Создает исключение, которое является результатом запроса неподдерживаемой возможности.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowresourceexceptiona--afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 Исключение ресурсов.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается, когда ресурсов Windows не удается загрузить.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowuserexceptiona--afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserException  
 Создает исключение для остановки операции пользователя.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается сразу после `AfxMessageBox` сообщил об ошибке для пользователя.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowoledispatchexceptiona--afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
 Эта функция используется для создания исключения в функцию автоматизации OLE.  
  
```   
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,  
    LPCSTR lpszDescription,  
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,  
    UINT nDescriptionID,  
    UINT nHelpID = -1); 
```  
  
### <a name="parameters"></a>Параметры  
 `wCode`  
 Код ошибки, присущие приложению.  
  
 `lpszDescription`  
 Словесное описание ошибки.  
  
 `nDescriptionID`  
 Идентификатор ресурса для описания устные ошибки.  
  
 `nHelpID`  
 Контекст справки для справки в приложении (. Файл HLP).  
  
### <a name="remarks"></a>Примечания  
 Управляющее приложение (Microsoft Visual Basic или другого клиентского приложения автоматизации OLE) могут отображаться сведения, предоставленные данной функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCExceptions&#25;](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxthrowoleexceptiona--afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleException  
 Создает объект типа `COleException` и создает исключение.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>Параметры  
 `sc`  
 Код состояния OLE, указывающее причину возникновения исключения.  
  
 `hr`  
 Дескриптор результирующий код, который указывает причину возникновения исключения.  
  
### <a name="remarks"></a>Примечания  
 Версия, принимающая `HRESULT` как аргумент преобразует этот код результата в соответствующий `SCODE`. Дополнительные сведения о `HRESULT` и `SCODE`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="a-nameafxthrowdaoexceptiona--afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 Эта функция вызывается для создания исключения типа [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>Параметры  
 `nAfxDaoError`  
 Целое число, представляющее DAO расширенный код ошибки, которой может принимать одно из значений, перечисленных в разделе [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).  
  
 *SCODE*  
 Код ошибки OLE из DAO типа `SCODE`. Сведения см. в разделе [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).  
  
### <a name="remarks"></a>Примечания  
 Платформа также вызывает `AfxThrowDaoException`. При выполнении вызова можно передать один из параметров или оба. Например, если необходимо изменить один из ошибок, определенные в **CDaoException::nAfxDaoError** , но не важна для вас *scode* параметр, передать допустимый код в `nAfxDaoError` параметр и принять значение по умолчанию для *scode*.  
  
 Дополнительные сведения об исключениях, связанные с классами MFC DAO см `CDaoException` в этой книге и статью [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
  
##  <a name="a-nameafxthrowdbexceptiona--afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException  
 Эта функция вызывается для создания исключения типа `CDBException` из собственного кода.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>Параметры  
 `nRetCode`  
 Значение типа **RETCODE**, определяющий тип ошибки, вызвавшей исключение.  
  
 `pdb`  
 Указатель на `CDatabase` объект, представляющий соединение с источником данных с которым связано это исключение.  
  
 `hstmt`  
 ODBC **HSTMT** дескриптор, который задает дескриптор инструкции, с которым связано это исключение.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает функцию `AfxThrowDBException` при получении ODBC **RETCODE** из вызова API-интерфейса ODBC функции и интерпретирует **RETCODE** как исключительное условие, а не ошибку expectable. Например операция доступа к данным может завершиться ошибкой из-за ошибки чтения диска.  
  
 Сведения о **RETCODE** значения, определенные в ODBC, содержатся в главе 8 «Получение состояния и сведения об ошибках,» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Сведения о MFC в этих кодов см. класс [CDBException](../../mfc/reference/cdbexception-class.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="a-nameafxaborta--afxabort"></a><a name="afxabort"></a>AfxAbort  
 Функции завершения по умолчанию, предоставляемой MFC.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>Примечания  
 `AfxAbort`вызывается внутренне, функции-члены MFC при Неустранимая ошибка, например неперехваченное исключение, которое не может быть обработан. Можно вызвать `AfxAbort` в редких случаях при возникновении неустранимой ошибки невозможно восстановить.  
  
### <a name="example"></a>Пример  
 В примере показано [CATCH](#catch).  

### <a name="requirements"></a>Требования  
  **Заголовок** afx.h   
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)

