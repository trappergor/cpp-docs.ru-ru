---
title: Обработка исключений
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.exceptions
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
ms.openlocfilehash: 6f74f0fcef7f9dc63138dcdb29487120818974f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651416"
---
# <a name="exception-processing"></a>Обработка исключений

При выполнении программы, может возникнуть ряд аномальных состояний и ошибок, называется «исключения». Они могут включать нехватку памяти, ошибки выделения ресурсов и не удалось найти файлы.

Библиотеки Microsoft Foundation Class использует схему обработки исключений, смоделированного точно один комитетом стандартов ANSI, предложенные для C++. Обработчик исключений необходимо настроить, прежде чем вызов функции, могут возникнуть нестандартной ситуации. Если функция обнаруживает об аномальных, выдает исключение, и управление передается обработчику исключений.

Обработчики исключений, устанавливаются несколько макросов, в состав библиотеки Microsoft Foundation Class. Ряд других глобальные функции помогают создавать специализированные исключения и завершение программы, при необходимости. Эти макросы и глобальные функции делятся на следующие категории:

- Макросы исключений, которые структура обработчик исключений.

- Exception-throwing функции), который создают исключения определенных типов.

- Функции завершения, которые вызывают завершение программы.

Примеры и Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="exception-macros"></a>Макросы исключений

|||
|-|-|
|[ПОПРОБУЙТЕ](#try)|Определяет блок кода для обработки исключений.|
|[CATCH](#catch)|Определяет блок кода для перехвата исключения из предыдущей **попробуйте** блока.|
|[CATCH_ALL](#catch_all)|Определяет блок кода для перехвата всех исключений из предыдущей **попробуйте** блока.|
|[AND_CATCH](#and_catch)|Определяет блок кода для перехвата исключений дополнительные типы из предыдущей **попробуйте** блока.|
|[AND_CATCH_ALL](#and_catch_all)|Определяет блок кода для перехвата всех других типов дополнительным исключением, исключение в предыдущем **попробуйте** блока.|
|[END_CATCH](#end_catch)|Завершает последний **CATCH** или **AND_CATCH** блок кода.|
|[END_CATCH_ALL](#end_catch_all)|Завершает последний **CATCH_ALL** блок кода.|
|[THROW](#throw)|Выдает указанное исключение.|
|[THROW_LAST](#throw_last)|В настоящее время обработано исключение для следующего внешнего обработчика.|

### <a name="exception-throwing-functions"></a>Функции, создающие исключения

|||
|-|-|
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Создает исключение архива.|
|[AfxThrowFileException](#afxthrowfileexception)|Исключение файла.|
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|Создает исключение недопустимого аргумента.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Исключение памяти.|
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Исключение не поддерживаются.|
|[AfxThrowResourceException](#afxthrowresourceexception)|Исключение Windows ресурс не найден.|
|[AfxThrowUserException](#afxthrowuserexception)|Создает исключение, в рамках программы, инициированного пользователем операции.|

MFC предоставляет две функции, создающие исключения специально для исключения OLE:

### <a name="ole-exception-functions"></a>Функции исключения OLE

|||
|-|-|
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Выдает исключение в функцию автоматизации OLE.|
|[AfxThrowOleException](#afxthrowoleexception)|Создает исключение OLE.|

Для поддержки исключения базы данных, классы базы данных предоставляют два классы исключений, `CDBException` и `CDaoException`и глобальные функции для поддержки типов исключений:

### <a name="dao-exception-functions"></a>Исключение функции DAO

|||
|-|-|
|[AfxThrowDAOException](#afxthrowdaoexception)|Создает [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.|
|[AfxThrowDBException](#afxthrowdbexception)|Создает [CDBException](../../mfc/reference/cdbexception-class.md) из собственного кода.|

MFC предоставляет следующие функции завершения:

### <a name="termination-functions"></a>Функции завершения

|||
|-|-|
|[AfxAbort](#afxabort)|Вызывается для завершения работы приложения при возникновении неустранимой ошибки происходит.|

##  <a name="try"></a>  ПОПРОБУЙТЕ

Настраивает **попробуйте** блока.

```
TRY
```

### <a name="remarks"></a>Примечания

Объект **попробуйте** блока определяет блок кода, который может выдавать исключения. Эти исключения обрабатываются в следующем **CATCH** и **AND_CATCH** блоков. Рекурсия разрешена: исключения может передаваться в внешний **попробуйте** блока, либо, пропуская их, либо с помощью throw_last-макрос. Конец **попробуйте** блок макросом END_CATCH или END_CATCH_ALL.

Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

См. в примере [CATCH](#catch).

### <a name="requirements"></a>Требования

Заголовок: afx.h

##  <a name="catch"></a>  CATCH

Определяет блок кода, который перехватывает первый тип исключения, созданного в предыдущем **попробуйте** блока.

```
CATCH(exception_class, exception_object_pointer_name)

```

### <a name="parameters"></a>Параметры

*exception_class*<br/>
Указывает тип исключения для проверки. Список стандартных классов исключений, см. в разделе класса [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Указывает имя указатель на объект исключения, будет создан в макросе. Указатель на имя можно использовать для доступа к объекту исключения в **CATCH** блока. Эта переменная объявляется для вас.

### <a name="remarks"></a>Примечания

Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретную причину исключения. Вызовите throw_last-макрос для сдвига обработки к следующему кадру внешнее исключение. Конец **попробуйте** блок с end_catch-макрос.

Если *exception_class* — это класс `CException`, а затем все типы исключение будет перехвачено. Можно использовать [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) функция-член для определения того, какое именно исключение, выданное. Для перехвата нескольких типов исключений, лучше использовать последовательные **AND_CATCH** инструкций, каждая из которых исключение другого типа.

Указатель на объект исключения создается макросом. Необходимо объявить ее самостоятельно.

> [!NOTE]
>  **CATCH** блока определяется как области C++, разделенные символами фигурные скобки. При объявлении переменных в этой области, они доступны только в пределах этой области. Это также относится к *exception_object_pointer_name*.

Дополнительные сведения и макрос CATCH исключений см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCExceptions#26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]

##  <a name="catch_all"></a>  CATCH_ALL

Определяет блок кода, который перехватывает все типы исключений, вызванных в предыдущем **попробуйте** блока.

```
CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer_name*<br/>
Указывает имя указатель на объект исключения, будет создан в макросе. Указатель на имя можно использовать для доступа к объекту исключения в `CATCH_ALL` блока. Эта переменная объявляется для вас.

### <a name="remarks"></a>Примечания

Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретную причину исключения. Вызвать `THROW_LAST` макрос для сдвига обработки к следующему кадру внешнее исключение. Если вы используете **CATCH_ALL**, end **попробуйте** блок с end_catch_all-макрос.

> [!NOTE]
>  **CATCH_ALL** блока определяется как области C++, разделенные символами фигурные скобки. При объявлении переменных в этой области, они доступны только в пределах этой области.

Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

См. в примере [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="and_catch"></a>  AND_CATCH

Определяет блок кода для перехвата типа дополнительных исключений, исключение в предыдущем **попробуйте** блока.

```
AND_CATCH(exception_class, exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_class*<br/>
Указывает тип исключения для проверки. Список стандартных классов исключений, см. в разделе класса [CException](../../mfc/reference/cexception-class.md).

*exception_object_pointer_name*<br/>
Имя указатель на объект исключения, будет создан в макросе. Указатель на имя можно использовать для доступа к объекту исключения в **AND_CATCH** блока. Эта переменная объявляется для вас.

### <a name="remarks"></a>Примечания

Используйте макрос CATCH для перехвата один тип исключения, а затем and_catch-макрос для каждого последующего типа. Конец **попробуйте** блок с end_catch-макрос.

Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретную причину исключения. Вызовите throw_last-макрос в **AND_CATCH** блок обработки к следующему кадру внешнее исключение shift. **AND_CATCH** отмечает конец предыдущего **CATCH** или **AND_CATCH** блока.

> [!NOTE]
>  **AND_CATCH** блока определяется как области C++ (разделенные символами фигурные скобки). При объявлении переменных в этой области, помните, что они доступны только внутри этой области. Это также относится к *exception_object_pointer_name* переменной.

### <a name="example"></a>Пример

См. в примере [CATCH](#catch).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h
##  <a name="and_catch_all"></a>  AND_CATCH_ALL

Определяет блок кода для перехвата типа дополнительных исключений, исключение в предыдущем **попробуйте** блока.

```
AND_CATCH_ALL(exception_object_pointer_name)
```

### <a name="parameters"></a>Параметры

*exception_object_pointer_name*<br/>
Имя указатель на объект исключения, будет создан в макросе. Указатель на имя можно использовать для доступа к объекту исключения в **AND_CATCH_ALL** блока. Эта переменная объявляется для вас.

### <a name="remarks"></a>Примечания

Используйте **CATCH** макрос для перехвата один тип исключения, а затем and_catch_all-макрос для перехвата всех других последующих типов. Если вы используете AND_CATCH_ALL, в конце **попробуйте** блок с end_catch_all-макрос.

Код обработки исключений можно запросить объект исключения, при необходимости получить дополнительные сведения о конкретную причину исключения. Вызовите throw_last-макрос в **AND_CATCH_ALL** блок обработки к следующему кадру внешнее исключение shift. **AND_CATCH_ALL** отмечает конец предыдущего **CATCH** или **AND_CATCH_ALL** блока.

> [!NOTE]
>  **AND_CATCH_ALL** блока определяется как области C++ (разделенные символами фигурные скобки). При объявлении переменных в этой области, помните, что они доступны только внутри этой области.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="end_catch"></a>  END_CATCH

Помечает конец последнего **CATCH** или **AND_CATCH** блока.

```
END_CATCH
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о end_catch-макрос см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="end_catch_all"></a>  END_CATCH_ALL

Помечает конец последнего ** CATCH_ALL88 или **AND_CATCH_ALL** блока.

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

*exception_object_pointer*<br/>
Указывает на объект исключения производным от `CException`.

### <a name="remarks"></a>Примечания

**ИСКЛЮЧЕНИЕ** прервет выполнение, передачу элементов управления в связанный программы **CATCH** блокировки в программе. Если вы не указали **CATCH** заблокировать, а затем управление передается модулю библиотеки Microsoft Foundation Class, который выводит ошибку, сообщение и завершает работу.

Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="throw_last"></a>  THROW_LAST

Это исключение обратно к следующему внешнего **CATCH** блока.

```
THROW_LAST()
```

### <a name="remarks"></a>Примечания

Этот макрос можно локально созданного исключения. При попытке создать исключение, вы могли просто выявить, он будет обычно выходят за пределы области действия и удалить. С помощью **THROW_LAST**, исключение передается правильно к следующему **CATCH** обработчика.

Дополнительные сведения см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).

### <a name="example"></a>Пример

См. в примере [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="afxthrowarchiveexception"></a>  AfxThrowArchiveException

Создает исключение архива.

```
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName);
```

### <a name="parameters"></a>Параметры

*Причина*<br/>
Указывает целое число, указывающее причину возникновения исключения. Список возможных значений, см. в разделе [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).

*lpszArchiveName*<br/>
Указывает на строку, содержащую имя `CArchive` объекта, вызвавшего исключение (если доступно).

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

*Причина*<br/>
Указывает целое число, указывающее причину возникновения исключения. Список возможных значений, см. в разделе [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).

*lOsError*<br/>
Содержит номер ошибки операционной системы (если доступно), указывающее причину возникновения исключения. См. в разделе документации операционной системы, список кодов ошибок.

*lpszFileName*<br/>
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

Эта функция вызывается в том случае, если используются недопустимые аргументы.

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс CInvalidArgException](cinvalidargexception-class.md)<br/>
[THROW](#throw)

##  <a name="afxthrowmemoryexception"></a>  AfxThrowMemoryException

Исключение памяти.

```
void AfxThrowMemoryException();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, если вызовы к базовой системе памяти Распределители (такие как **malloc** и [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) функции Windows) завершиться ошибкой. Не нужно вызывать его для **новый** поскольку **новый** создаст исключение памяти автоматически, если выделение памяти завершается сбоем.

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="afxthrownotsupportedexception"></a>  AfxThrowNotSupportedException

Создает исключение, которое является результатом запроса неподдерживаемой возможности.

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

Эту функцию можно используйте для создания исключения в функцию автоматизации OLE.

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

*WCode*<br/>
Код ошибки, характерные для вашего приложения.

*lpszDescription*<br/>
Словесное описание ошибки.

*nDescriptionID*<br/>
Идентификатор ресурса для описания устные ошибки.

*nHelpID*<br/>
Контекст справки для получения справки в приложении (. Файл HLP).

### <a name="remarks"></a>Примечания

Вождения приложением (Microsoft Visual Basic или другом клиентском приложении модели автоматизации OLE) могут отображаться сведения, предоставленные данной функции.

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

*SC*<br/>
Код состояния OLE, указывающее причину возникновения исключения.

*hr*<br/>
Дескриптор результирующий код, который указывает причину возникновения исключения.

### <a name="remarks"></a>Примечания

Версия, которая принимает значение HRESULT в качестве аргумента преобразует этот код результата в соответствующий SCODE. Дополнительные сведения о HRESULT и SCODE, см. в разделе [структуры из кодов ошибок модели COM](/windows/desktop/com/structure-of-com-error-codes) в пакете Windows SDK.

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="afxthrowdaoexception"></a>  AfxThrowDaoException

Вызывайте эту функцию для создания исключения типа [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.

```
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,
    SCODE scode = S_OK);
```

### <a name="parameters"></a>Параметры

*nAfxDaoError*<br/>
Целое число, представляющее DAO расширенный код ошибки, который может принимать одно из значений перечисленных в разделе [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).

*SCODE*<br/>
Код ошибки OLE из DAO типа SCODE. Сведения см. в разделе [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).

### <a name="remarks"></a>Примечания

Платформа также вызывает `AfxThrowDaoException`. При выполнении вызова можно передать один из параметров или оба. Например, если вы хотите вызвать один из ошибок, определенные в **CDaoException::nAfxDaoError** , но вы не важна *scode* параметра, передайте допустимый код в *nAfxDaoError* параметр и примите значение по умолчанию для *scode*.

Сведения об исключениях, связанные с классами MFC DAO см. в разделе класса `CDaoException` в этой книге и в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

##  <a name="afxthrowdbexception"></a>  AfxThrowDBException

Вызывайте эту функцию для создания исключения типа `CDBException` из собственного кода.

```
void AfxThrowDBException(
    RETCODE nRetCode,
    CDatabase* pdb,
    HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
Значение типа RETCODE, определяющий тип ошибки, вызвавшей исключение.

*PDB-файл*<br/>
Указатель на `CDatabase` объект, представляющий соединение с источником данных с которым связано исключение.

*HSTMT*<br/>
Дескриптор ODBC HSTMT, который указывает дескриптор инструкции, с которым связано исключение.

### <a name="remarks"></a>Примечания

Платформа вызывает `AfxThrowDBException` при получении RETCODE ODBC из вызова функции ODBC API и интерпретирует RETCODE как исключительным условием, а не ошибку expectable. Например операция доступа к данным может завершиться ошибкой из-за ошибки с диска.

Сведения о значениях RETCODE, определенном ODBC см «Получение состояния и сведения об ошибке,» в пакете Windows SDK. Сведения о MFC в этих кодов см. в разделе класса [CDBException](../../mfc/reference/cdbexception-class.md).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

##  <a name="afxabort"></a>  AfxAbort

Функция завершения по умолчанию, предоставляемые MFC.

```
void  AfxAbort();
```

### <a name="remarks"></a>Примечания

`AfxAbort` можно вызвать изнутри функциями-членами MFC, при возникновении неустранимой ошибки, например, неперехваченное исключение, которое невозможно обработать. Вы можете вызвать `AfxAbort` в тех редких случаях при возникновении неустранимой ошибки, из которой невозможно восстановить.

### <a name="example"></a>Пример

См. в примере [CATCH](#catch).

### <a name="requirements"></a>Требования

  **Заголовок** afx.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
