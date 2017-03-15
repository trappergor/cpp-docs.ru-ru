---
title: "CException-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CException
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException class, base class
- CException class
- exceptions, classes for
- CInternetException class, base class
- macros, exception handling
- CNotSupportedException class, base class
- CFileException class, base class
- CDBException class, base class
- CArchiveException class, base class
- CUserException class
- CDaoException class, base class
- CMemoryException class, base class
- COleException class, base class
- CResourceException class, base class
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
caps.latest.revision: 22
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4cbb69ff79a1b201260d83b1bd568b63519a33b5
ms.lasthandoff: 02/24/2017

---
# <a name="cexception-class"></a>CException-класс
Базовый класс для всех исключений библиотеки классов Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CException::CException](#cexception)|Создает объект `CException`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CException::Delete](#delete)|Удаляет `CException` объекта.|  
|[CException::ReportError](#reporterror)|Возвращает сообщение об ошибке в окне сообщения пользователю.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку `CException` — абстрактный базовый класс, не удается создать `CException` объектов непосредственно, необходимо создать объекты из производных классов. Если необходимо создать свой собственный `CException`-класс стиля, используйте один из производных классов, перечисленных выше, как модель. Убедитесь, что производный класс также используется `IMPLEMENT_DYNAMIC`.  
  
 Производные классы и их описания приведены ниже:  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Базовый класс для исключений ресурсов с точки зрения MFC|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Условие исключения недопустимый аргумент|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запрос неподдерживаемая операция|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Исключения для конкретных архива|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|Исключение файлов|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows, не найден или не создаваемый объект|  
|[COleException](../../mfc/reference/coleexception-class.md)|Исключения OLE|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|Исключение базы данных (то есть, условия возникновения исключений поступающее для классов баз данных MFC на основе на Open Database Connectivity)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Исключение OLE диспетчеризации (автоматизация)|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, которое указывает, что ресурс не найден|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Доступ к данным объект исключения (то есть, условия возникновения исключений поступающее для классов DAO)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Исключение Интернет (то есть, условия возникновения исключений поступающее для классов в Интернете).|  
  
 Они предназначены для использования с [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [попробуйте](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), и [end_catch](exception-processing.md#end_catch) макросы. Дополнительные сведения об исключениях см. в разделе [обработка исключений](exception-processing.md), или обратитесь к статье [обработка исключений (MFC)](../exception-handling-in-mfc.md).  
  
 Для перехвата определенного исключения, используйте соответствующий производный класс. Для типов перехватывать все исключения, используйте `CException`, а затем использовать [CObject::IsKindOf](cobject-class.md#iskindof) для различения `CException`-производные классы. Обратите внимание, что `CObject::IsKindOf` работает только для классов, объявленные с [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) макрос, чтобы воспользоваться преимуществами динамической проверки типов. Любой `CException`-следует использовать производный класс, который создается `IMPLEMENT_DYNAMIC` макрос, слишком.  
  
 Можно сообщать сведения об исключениях для пользователя путем вызова [GetErrorMessage](cfileexception-class.md#geterrormessage) или [ReportError](#reporterror), два члена функции, которые работают с любым из `CException`производных классов.  
  
 Если исключение перехватывается один из макросов, `CException` объект удаляется автоматически, не удаляйте его самостоятельно. Если исключение перехватывается с помощью **catch** ключевое слово, он не удаляется автоматически. См. в статье [обработка исключений (MFC)](../exception-handling-in-mfc.md) Дополнительные сведения о том удалить объект сведения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](cobject-class.md)  
  
 `CException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="a-namecexceptiona--cexceptioncexception"></a><a name="cexception"></a>CException::CException  
 Эта функция-член создает `CException` объекта.  
  
```  
explicit CException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *b_AutoDelete*  
 Укажите **TRUE** Если память для `CException` объект выделен в куче. Это приведет к `CException` объект для удаления при **удаление** функция-член вызывается для удаления исключения. Укажите **FALSE** Если `CException` объект в стеке или — это глобальный объект. В этом случае `CException` объект не будет удален при **удаление** вызывается функция-член.  
  
### <a name="remarks"></a>Примечания  
 Напрямую вызывать этот конструктор обычно никогда не потребуется. Функция, которая создает исключение должно создать экземпляр `CException`-производный класс и вызывать его конструктор, или воспользуйтесь одним из MFC вызывает функции, такие как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), чтобы создавать предопределенные типа. Эта документация предоставляется только для обеспечения полноты.  
  
##  <a name="a-namedeletea--cexceptiondelete"></a><a name="delete"></a>CException::Delete  
 Эта функция проверяет **CException** объект был создан в куче, и если да, вызывает **удаление** оператор в объекте.  
  
```  
void Delete();
```  
  
### <a name="remarks"></a>Примечания  
 При удалении **CException** , используйте **удаление** функция-член для удаления исключения. Не используйте **удаление** оператор напрямую, поскольку `CException` объекта может быть глобального объекта или были созданы в стеке.  
  
 Можно указать, должен ли объект удален при создании объекта. Дополнительные сведения см. в разделе [CException::CException](#cexception).  
  
 Необходимо вызвать **удаление** при использовании C++ **попробуйте**- **catch** механизм. При использовании макросов MFC **попробуйте** и **CATCH**, а затем эти макросы автоматически вызывает эту функцию.  
  
### <a name="example"></a>Пример  
 ```cpp  
 CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the 
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}   
 ```
  
##  <a name="a-namereporterrora--cexceptionreporterror"></a><a name="reporterror"></a>CException::ReportError  
 Вызовите эту функцию-член в текст отчета об ошибках в окне сообщения для пользователя.  
  
```  
virtual int ReportError(
    UINT nType = MB_OK,  
    UINT nMessageID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nType`  
 Задает стиль окна сообщения. Примените любое сочетание [стили окна сообщений](message-box-styles.md) в поле. Если этот параметр не задан, по умолчанию используется **MB_OK**.  
  
 *nMessageID*  
 Указывает идентификатор ресурса (записи в таблицу строк) сообщение, отображаемое, если объект исключения отсутствует сообщение об ошибке. Если значение равно 0, сообщения» нет сообщение об ошибке недоступно» отображается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `AfxMessageBox` Значение; в противном случае — 0, если не хватает памяти для отображения в окне сообщения. В разделе [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) для возможные возвращаемые значения.  
  
### <a name="example"></a>Пример  
 Ниже приведен пример использования `CException::ReportError`. Другой пример, см. пример для [CATCH](exception-processing.md#catch).  
  
```cpp  
CFile fileInput;
CFileException ex;

// try to open a file for reading.  
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>См. также  
 [CObject-класс](cobject-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)   
 [Обработка исключений](exception-processing.md)   
 [Практические советы. Создание собственных классов пользовательских исключений](http://go.microsoft.com/fwlink/linkid=128045)



