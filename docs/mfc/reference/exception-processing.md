---
title: Исключение при обработке | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exception handling
- DAO (Data Access Objects), exceptions [MFC]
- OLE exceptions [MFC], MFC functions
- exceptions [MFC], processing
- exception macros [MFC]
- termination functions, MFC
- MFC, exceptions
- exceptions [MFC], MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a24d78089e468a2020e0ecdb1fba34783965325
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exception-processing"></a>Обработка исключений
Когда программа выполняется, может возникнуть ряд нештатных ситуаций и ошибки называемые «исключения». Это могут быть нехватка памяти, ошибки выделения ресурсов и не удалось найти файлы.  
  
 Библиотеки классов Microsoft Foundation использует схему обработки исключений, который тесно моделируется после одного комитетом стандартов ANSI, предложенные для C++. Обработчик исключений необходимо настроить до вызова функции, могут возникнуть нестандартной ситуации. Если функция обнаруживает нестандартных условий, выдает исключение и управление передается обработчику исключений.  
  
 Несколько макросов, входящий в состав библиотеки классов Microsoft Foundation настроите обработчиков исключений. Ряд других глобальные функции помогают создавать специализированные исключения и завершить работу программы, при необходимости. Эти макросы и глобальные функции делятся на следующие категории:  
  
- Макросы исключений, которые структуры обработчик исключений.  
  
- Exception-throwing функции), который создал исключения определенных типов.  
  
- Функции завершения, которые вызывают завершение программы.  
  
 Примеры и Дополнительные сведения, см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="exception-macros"></a>Макросы исключений  
  
|||  
|-|-|  
|[ПОПРОБУЙТЕ](#try)|Определяет блок кода для обработки исключения.|  
|[CATCH](#catch)|Определяет блок кода для перехвата исключения из указанных выше **ПОВТОРИТЕ** блока.|  
|[CATCH_ALL](#catch_all)|Определяет блок кода для перехвата всех исключений из указанных выше **ПОВТОРИТЕ** блока.|  
|[AND_CATCH](#and_catch)|Определяет блок кода для перехвата дополнительные типы из указанных выше **ПОВТОРИТЕ** блока.|  
|[AND_CATCH_ALL](#and_catch_all)|Определяет блок кода для перехвата всех других типов дополнительные исключения, возникшие в предыдущем **ПОВТОРИТЕ** блока.|  
|[END_CATCH](#end_catch)|Завершает последний **ПЕРЕХВАТЫВАТЬ** или `AND_CATCH` блок кода.|  
|[END_CATCH_ALL](#end_catch_all)|Завершает последний `CATCH_ALL` блок кода.|  
|[THROW](#throw)|Выдает указанное исключение.|  
|[THROW_LAST](#throw_last)|В настоящее время обработано исключение в обработчик следующий outer.|  
  
### <a name="exception-throwing-functions"></a>Функции, создающие исключения  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Создает исключение архива.|  
|[AfxThrowFileException](#afxthrowfileexception)|Исключение файла.|  
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Создает исключение недопустимого аргумента.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Исключение памяти.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Исключение не поддерживаются.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Исключение Windows ресурса не найден.|  
|[AfxThrowUserException](#afxthrowuserexception)|Возникло исключение в действии пользователь запустил программу.|  
  
 MFC предоставляет две функции, создающие исключения специально для исключения OLE:  
  
### <a name="ole-exception-functions"></a>Функции исключения OLE  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Вызывает исключение в пределах функции автоматизации OLE.|  
|[AfxThrowOleException](#afxthrowoleexception)|Создает исключение OLE.|  
  
 Для поддержки исключения базы данных, классы базы данных предоставляют два класса исключения `CDBException` и `CDaoException`и глобальные функции для поддержки типов исключений:  
  
### <a name="dao-exception-functions"></a>Исключения функции DAO  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Создает [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.|  
|[AfxThrowDBException](#afxthrowdbexception)|Создает [CDBException](../../mfc/reference/cdbexception-class.md) из собственного кода.|  
  
 MFC предоставляет следующие функции завершения:  
  
### <a name="termination-functions"></a>Функции завершения  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|Вызывается для завершения приложения при Неустранимая ошибка возникает.|  
  
##  <a name="try"></a>  ПОПРОБУЙТЕ  
 Настраивает **ПОВТОРИТЕ** блока.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>Примечания  
 Объект **ПОВТОРИТЕ** блок определяет блок кода, который может создавать исключения. Эти исключения обрабатываются в следующем **ПЕРЕХВАТЫВАТЬ** и `AND_CATCH` блоков. Рекурсия разрешена: исключения может передаваться внешний **ПОВТОРИТЕ** блока, игнорируя их или используя `THROW_LAST` макрос. Конец **ПОВТОРИТЕ** блоке с `END_CATCH` или `END_CATCH_ALL` макрос.  
  
 Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [ПЕРЕХВАТЫВАТЬ](#catch).  

### <a name="requirements"></a>Требования
Заголовок: afx.h

##  <a name="catch"></a>  CATCH  
 Определяет блок кода, который перехватывает первый тип исключения, возникшие в предыдущем **ПОВТОРИТЕ** блока.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>Параметры  
 *exception_class*  
 Указывает тип исключения для проверки. Список классов стандартных исключений, см. класс [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Указывает имя для указателя на объект исключения, создаваемой в макросе. Имя указателя можно использовать для доступа к объекту исключения в **ПЕРЕХВАТЫВАТЬ** блока. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Код обработки исключения может запрашивать объекта исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызов `THROW_LAST` макрос для сдвига обработки на следующий кадр внешнее исключение. Конец **ПОВТОРИТЕ** блоке с `END_CATCH` макрос.  
  
 Если *exception_class* класс `CException`, а затем все типы исключение будет перехвачено. Можно использовать [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) функции-члена для определения того, какое именно исключение было создано. Для перехвата несколько типов исключений, лучше использовать последовательные `AND_CATCH` операторов с другой тип исключения.  
  
 Указатель на объект исключения создается макросом. Необходимо объявить его.  
  
> [!NOTE]
>  **ПЕРЕХВАТЫВАТЬ** блока определяется как области C++, разделенные символами фигурные скобки. При объявлении переменных в этой области, они доступны только в пределах данной области. Это также относится к *exception_object_pointer_name*.  
  
 Дополнительные сведения об исключениях и **ПЕРЕХВАТЫВАТЬ** макрос, см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="catch_all"></a>  CATCH_ALL  
 Определяет блок кода, который перехватывает все типы исключений, вызванных в предыдущем **ПОВТОРИТЕ** блока.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *exception_object_pointer_name*  
 Указывает имя для указателя на объект исключения, создаваемой в макросе. Имя указателя можно использовать для доступа к объекту исключения в `CATCH_ALL` блока. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Код обработки исключения может запрашивать объекта исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызов `THROW_LAST` макрос для сдвига обработки на следующий кадр внешнее исключение. Если вы используете `CATCH_ALL`, end **ПОВТОРИТЕ** блоке с `END_CATCH_ALL` макрос.  
  
> [!NOTE]
>  `CATCH_ALL` Блока определяется как области C++, разделенные символами фигурные скобки. При объявлении переменных в этой области, они доступны только в пределах данной области.  
  
 Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  

##  <a name="and_catch"></a>  AND_CATCH  
 Определяет блок кода для перехвата типы дополнительные исключения, исключение в предыдущем **ПОВТОРИТЕ** блока.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *exception_class*  
 Указывает тип исключения для проверки. Список классов стандартных исключений, см. класс [CException](../../mfc/reference/cexception-class.md).  
  
 *exception_object_pointer_name*  
 Имя для указателя на объект исключения, создаваемой в макросе. Имя указателя можно использовать для доступа к объекту исключения в `AND_CATCH` блока. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Используйте **ПЕРЕХВАТЫВАТЬ** макрос для перехвата один тип исключения, то `AND_CATCH` макрос для перехвата всех последующих типов. Конец **ПОВТОРИТЕ** блоке с `END_CATCH` макрос.  
  
 Код обработки исключения может запрашивать объекта исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызовите `THROW_LAST` макрос в `AND_CATCH` блока обработки на следующий кадр внешнее исключение shift. `AND_CATCH` отмечает конец предыдущего **ПЕРЕХВАТЫВАТЬ** или `AND_CATCH` блока.  
  
> [!NOTE]
>  `AND_CATCH` Блока определяется как область C++ (пользователь, фигурные скобки). При объявлении переменных в этой области, помните, что доступный только внутри этой области. Это также относится к *exception_object_pointer_name* переменной.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [ПЕРЕХВАТЫВАТЬ](#catch).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
##  <a name="and_catch_all"></a>  AND_CATCH_ALL  
 Определяет блок кода для перехвата типы дополнительные исключения, исключение в предыдущем **ПОВТОРИТЕ** блока.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>Параметры  
 *exception_object_pointer_name*  
 Имя для указателя на объект исключения, создаваемой в макросе. Имя указателя можно использовать для доступа к объекту исключения в `AND_CATCH_ALL` блока. Эта переменная объявляется для вас.  
  
### <a name="remarks"></a>Примечания  
 Используйте **ПЕРЕХВАТЫВАТЬ** макрос для перехвата один тип исключения, то `AND_CATCH_ALL` макрос для перехвата всех остальных последующих типов. Если вы используете `AND_CATCH_ALL`, end **ПОВТОРИТЕ** блоке с `END_CATCH_ALL` макрос.  
  
 Код обработки исключения может запрашивать объекта исключения, при необходимости получить дополнительные сведения о конкретной причины исключения. Вызовите `THROW_LAST` макрос в `AND_CATCH_ALL` блока обработки на следующий кадр внешнее исключение shift. `AND_CATCH_ALL` отмечает конец предыдущего **ПЕРЕХВАТЫВАТЬ** или `AND_CATCH_ALL` блока.  
  
> [!NOTE]
>  `AND_CATCH_ALL` Блока определяется как область C++ (пользователь, фигурные скобки). При объявлении переменных в этой области, помните, что доступный только внутри этой области.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="end_catch"></a>  END_CATCH  
 Отмечает конец последнего **ПЕРЕХВАТЫВАТЬ** или `AND_CATCH` блока.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о `END_CATCH` макрос, см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="end_catch_all"></a>  END_CATCH_ALL  
 Отмечает конец последнего `CATCH_ALL` или `AND_CATCH_ALL` блока.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="throw"></a>  THROW (MFC)  
 Выдает указанное исключение.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>Параметры  
 *exception_object_pointer*  
 Указывает на объект исключения производным от `CException`.  
  
### <a name="remarks"></a>Примечания  
 **ИСКЛЮЧЕНИЕ** прерывания выполнения, передачи управления в связанный обработчик программы **ПЕРЕХВАТЫВАТЬ** блокировки в приложении. Если вы не указали **ПЕРЕХВАТЫВАТЬ** заблокировать, а затем управление передается модуль библиотеки Microsoft Foundation Class, который выводит ошибку, сообщение и завершает работу.  
  
 Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="throw_last"></a>  THROW_LAST  
 Создает исключение обратно к следующему внешнего **ПЕРЕХВАТЫВАТЬ** блока.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>Примечания  
 Этот макрос позволяет локально созданного исключения. При попытке создать исключение, могли просто выявить, он обычно выйдут из области действия и удалить. С `THROW_LAST`, исключение передается правильно к следующему **ПЕРЕХВАТЫВАТЬ** обработчика.  
  
 Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrowarchiveexception"></a>  AfxThrowArchiveException  
 Создает исключение архива.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>Параметры  
 `cause`  
 Указывает целое число, указывающее причину создания исключения. Список возможных значений см. в разделе [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).  
  
 `lpszArchiveName`  
 Указывает строку, содержащую имя `CArchive` объекта, вызвавшего исключение (если доступно).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrowfileexception"></a>  AfxThrowFileException  
 Исключение файла.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `cause`  
 Указывает целое число, указывающее причину создания исключения. Список возможных значений см. в разделе [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).  
  
 `lOsError`  
 Содержит номер ошибки операционной системы (если доступно), указывающее причину создания исключения. В разделе документации операционной системы для получения списка кодов ошибок.  
  
 `lpszFileName`  
 Указывает строку, содержащую имя файла, вызвавшего исключение (если доступно).  
  
### <a name="remarks"></a>Примечания  
 Вы несете ответственность за определение причины, по коду ошибки операционной системы.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  

## <a name="afxthrowinvalidargexception"></a>  AfxThrowInvalidArgException
Создает исключение недопустимого аргумента.  
   
### <a name="syntax"></a>Синтаксис    
```
void AfxThrowInvalidArgException( );  
```  
   
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, когда используются недопустимые аргументы.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [Класс CInvalidArgException](cinvalidargexception-class.md)   
 [THROW](#throw)
  
  
##  <a name="afxthrowmemoryexception"></a>  AfxThrowMemoryException  
 Исключение памяти.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, если вызовы базового выделения памяти системы (например, `malloc` и [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) функции Windows) ошибкой. Необходимо вызвать его для **новый** из-за **новый** выдаст исключение памяти автоматически, если происходит сбой выделения памяти.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrownotsupportedexception"></a>  AfxThrowNotSupportedException  
 Создает исключение, являющееся результатом запроса неподдерживаемой возможности.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrowresourceexception"></a>  AfxThrowResourceException  
 Исключение ресурсов.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается, когда не удается загрузить ресурс Windows.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrowuserexception"></a>  AfxThrowUserException  
 Создает исключение для остановки операции пользователя.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается сразу после `AfxMessageBox` сообщил об ошибке для пользователя.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrowoledispatchexception"></a>  AfxThrowOleDispatchException  
 Эта функция используется для создания исключения в пределах функции автоматизации OLE.  
  
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
 Код ошибки, относящихся к конкретному приложению.  
  
 `lpszDescription`  
 Словесное описание ошибки.  
  
 `nDescriptionID`  
 Идентификатор ресурса для описания устные ошибки.  
  
 `nHelpID`  
 Контекст справки для получения справки приложения (. Файл HLP).  
  
### <a name="remarks"></a>Примечания  
 Эту информацию для этой функции может быть показан определяющим приложения (Microsoft Visual Basic или другое приложение клиента автоматизации OLE).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCExceptions#25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxthrowoleexception"></a>  AfxThrowOleException  
 Создает объект типа `COleException` и создает исключение.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>Параметры  
 `sc`  
 Код состояния OLE, указывающее причину создания исключения.  
  
 `hr`  
 Дескриптор результирующий код, который указывает причину возникновения исключения.  
  
### <a name="remarks"></a>Примечания  
 Версия, принимающая `HRESULT` как аргумент, код результата преобразует в соответствующий `SCODE`. Дополнительные сведения о `HRESULT` и `SCODE`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="afxthrowdaoexception"></a>  AfxThrowDaoException  
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
 Вызывается платформой `AfxThrowDaoException`. При выполнении вызова можно передать один из параметров или оба. Например, если необходимо изменить один из ошибок, определенные в **CDaoException::nAfxDaoError** , но не важна *scode* параметра, передайте допустимый код в `nAfxDaoError` параметра и принять значение по умолчанию для *scode*.  
  
 Сведения об исключениях, связанные с классами MFC DAO см. класс `CDaoException` в этой книге и статья [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
  
##  <a name="afxthrowdbexception"></a>  AfxThrowDBException  
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
 Платформа вызывает `AfxThrowDBException` при получении ODBC **RETCODE** из вызова API-интерфейса ODBC функцией и интерпретирует **RETCODE** как исключительным условием, а не ошибку expectable. Например операции доступа к данным может завершиться ошибкой из-за ошибки с диска.  
  
 Сведения о **RETCODE** значения, определенном ODBC см «Получение состояния и сведения об ошибке,» в Windows SDK. Сведения о MFC в этих кодов см. класс [CDBException](../../mfc/reference/cdbexception-class.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afx.h  
  
##  <a name="afxabort"></a>  AfxAbort  
 Функция завершения по умолчанию, предоставляемые MFC.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>Примечания  
 `AfxAbort` можно вызвать изнутри функциями-членами MFC, при наличии Неустранимая ошибка, например неперехваченное исключение, которое невозможно обработать. Можно вызвать `AfxAbort` в тех редких случаях, если возникла неустранимая ошибка, невозможно восстановить.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [ПЕРЕХВАТЫВАТЬ](#catch).  

### <a name="requirements"></a>Требования  
  **Заголовок** afx.h   
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Класс CException](../../mfc/reference/cexception-class.md)
