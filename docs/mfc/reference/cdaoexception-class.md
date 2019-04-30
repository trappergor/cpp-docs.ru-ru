---
title: Класс CDaoException
ms.date: 11/04/2016
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
ms.openlocfilehash: 8d49291c51f66ee837f9b31a2ade390cec48c51a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399808"
---
# <a name="cdaoexception-class"></a>Класс CDaoException

Представляет условие исключения, поступающее от классов базы данных MFC на базе объектов доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```
class CDaoException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CDaoException::CDaoException](#cdaoexception)|Создает объект `CDaoException`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDaoException::GetErrorCount](#geterrorcount)|Возвращает число ошибок в коллекцию ошибок для ядра СУБД.|
|[CDaoException::GetErrorInfo](#geterrorinfo)|Возвращает сведения об объекте конкретную ошибку в коллекцию ошибок.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|Содержит расширенный код ошибки для любой ошибки в классах MFC DAO.|
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Указатель на [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) , содержащий сведения о один объект ошибки DAO.|
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode) значение, связанное с ошибкой.|

## <a name="remarks"></a>Примечания

Этот класс включает членами общих данных, которые можно использовать для определения причины исключения. `CDaoException` объекты конструирования и вызванных функций-членов классов баз данных DAO.

> [!NOTE]
>  Классы баз данных DAO, отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классы MFC на основе ODBC; классы на основе DAO можно получить доступ к данных, в том числе через драйверы ODBC, с помощью собственных компонент database engine. Классы на основе DAO также поддерживают операции языка описания данных DDL, например добавление таблиц через классы, не нужно звонить DAO напрямую. Сведения об исключениях, выдаваемых классами ODBC см. в разделе [CDBException](../../mfc/reference/cdbexception-class.md).

Доступ к объектам исключение в пределах осуществляется [CATCH](../../mfc/reference/exception-processing.md#catch) выражение. Также может породить `CDaoException` объектов из кода с помощью [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) глобальной функции.

В MFC, все ошибки DAO выражаются в виде исключения типа `CDaoException`. При перехвате исключения этого типа можно использовать `CDaoException` функции-члены для получения сведений из любой объекты ошибок DAO, хранящихся в коллекции ошибок ядра СУБД. Как возникли ошибки, один или несколько объектов ошибка помещаются в коллекцию ошибок. (Обычно коллекция содержит только один объект ошибки; при использовании источника данных ODBC, скорее всего получить несколько объектов ошибок). Если другая операция DAO создает ошибку, снят в коллекцию ошибок, а новый объект ошибки помещается в коллекцию ошибок. DAO операций, которые не создают ошибку не оказывают влияния на в коллекцию ошибок.

Коды ошибок DAO см. в файле DAOERR. З. Дополнительные сведения см. в разделе «Перехватываемая данных доступа ошибки» в справке DAO.

Дополнительные сведения об обработке исключений в общие или о `CDaoException` объектов, см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключения: Базы данных исключений](../../mfc/exceptions-database-exceptions.md). Во второй статье содержится пример кода, демонстрируется обработка исключений в DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

##  <a name="cdaoexception"></a>  CDaoException::CDaoException

Создает объект `CDaoException`.

```
CDaoException();
```

### <a name="remarks"></a>Примечания

Как правило платформа создает объекты исключений при его код выдает исключение. Редко необходимо явно создать экземпляр объекта исключения. Если вы хотите создавать `CDaoException` из собственного кода, вызовите глобальную функцию [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).

Тем не менее можно явно создать экземпляр объекта исключения, при создании с помощью указателей на интерфейс DAO, которые инкапсулируют классы MFC DAO прямые вызовы. В этом случае может потребоваться получить сведения об ошибке из DAO. Предположим, что при вызове метода DAO через интерфейс DAODatabases коллекцию баз данных рабочей области в DAO возникает ошибка.

##### <a name="to-retrieve-the-dao-error-information"></a>Чтобы получить сведения об ошибке DAO

1. Создать `CDaoException` объекта.

1. Вызовите объект исключения [GetErrorCount](#geterrorcount) функция-член для определения, сколько ошибок объекты находятся в коллекцию ошибок для ядра СУБД. (Обычно имеет только один, если вы не используете источник данных ODBC.)

1. Вызовите объект исключения [GetErrorInfo](#geterrorinfo) функция-член для извлечения одного объекта ошибки одновременно, по индексу в коллекции, с помощью объекта исключения. Считать объект исключения прокси-сервер для одного объекта ошибки DAO.

1. Проверить текущую [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуру, в которой `GetErrorInfo` возвращает в [m_pErrorInfo](#m_perrorinfo) данные-член. Ее члены предоставляют сведения об этой ошибке DAO.

1. В случае с источником данных ODBC повторите шаги 3 и 4 при необходимости для дополнительные объекты ошибок.

1. Если вы создан объект исключения в куче, удалите его, используя **удалить** оператора после завершения.

Дополнительные сведения об обработке ошибок в классах MFC DAO см. в статье [исключения: Базы данных исключений](../../mfc/exceptions-database-exceptions.md).

##  <a name="geterrorcount"></a>  CDaoException::GetErrorCount

Вызовите эту функцию-член для получения числа объектов DAO об ошибке в коллекцию ошибок для ядра СУБД.

```
short GetErrorCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число объектов DAO ошибку в коллекцию ошибок для ядра СУБД.

### <a name="remarks"></a>Примечания

Эта информация полезна для перебора в коллекцию ошибок для получения каждого из них ошибка DAO один или несколько в коллекции. Чтобы получить объект ошибки по индексу или по номеру ошибки DAO, вызовите [GetErrorInfo](#geterrorinfo) функция-член.

> [!NOTE]
>  Обычно имеется только один объект ошибки в коллекцию ошибок. Если вы работаете с источником данных ODBC, однако возможны более одного.

##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo

Возвращает сведения об объекте конкретную ошибку в коллекцию ошибок.

```
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс сведения об ошибке в коллекцию ошибок ядра СУБД, для поиска по индексу.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию члена, чтобы получить следующую информацию об исключении:

- Код ошибки

- Source

- Описание

- Файл справки

- Контекст справки

`GetErrorInfo` Эти сведения хранятся в объекте исключения `m_pErrorInfo` элемент данных. Краткое описание сведений, возвращаемых, см. в разделе [m_pErrorInfo](#m_perrorinfo). Если производится перехват исключения с типом `CDaoException` выводится MFC, `m_pErrorInfo` член будет уже указано. Если вы решили вызов DAO напрямую, необходимо вызвать объект исключения `GetErrorInfo` функция-член для заполнения `m_pErrorInfo`. Более подробное описание см. в разделе [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуры.

Сведения об исключениях DAO и пример кода см. в статье [исключения: Базы данных исключений](../../mfc/exceptions-database-exceptions.md).

##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError

Содержит MFC расширенный код ошибки.

### <a name="remarks"></a>Примечания

Этот код предоставляется в случаях, где выдвигают определенный компонент классов MFC DAO.

Доступны следующие значения:

- NO_AFX_DAO_ERROR, самой последней операции не привел к MFC расширенное сообщение об ошибке. Тем не менее, операция может выдали другие ошибки из DAO или OLE, поэтому следует выполнять проверку [m_pErrorInfo](#m_perrorinfo) и, возможно, [m_scode](#m_scode).

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC не удалось инициализировать базы данных Microsoft Jet. OLE может не удалось инициализировать или было бы невозможно создать экземпляр объекта ядра базы данных DAO. Эти проблемы обычно предложить неправильная установка DAO или OLE.

- AFX_DAO_ERROR_DFX_BIND адрес, используемый в вызове функции exchange (DFX) полями записей DAO не существует или является недопустимым (адрес не использовался для привязки данных). Неправильный адрес может прошло в вызове DFX или адрес может оказаться недопустимым между операциями DFX.

- AFX_DAO_ERROR_OBJECT_NOT_OPEN была предпринята попытка открыть набор записей на основе querydef или объект tabledef, который не находилось в открытом состоянии.

##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo

Содержит указатель на `CDaoErrorInfo` структуру, которая содержит сведения о объекте ошибки DAO, вы извлекли путем вызова [GetErrorInfo](#geterrorinfo).

### <a name="remarks"></a>Примечания

Этот объект содержит следующие сведения:

|Член CDaoErrorInfo|Сведения|Значение|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|Код ошибки|Код ошибки DAO|
|`m_strSource`|Source|Имя объекта или приложения, вызвавшего ошибку|
|`m_strDescription`|Описание|Строку описания, связанный с ошибкой|
|`m_strHelpFile`|Файл справки|Путь к файлу справки Windows, в котором пользователь может получить информацию о проблеме|
|`m_lHelpContext`|Контекст справки|Идентификатор контекста для раздела в файле справки DAO|

Полные сведения об информации, содержащейся в `CDaoErrorInfo` объекта, см. в разделе [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуры.

##  <a name="m_scode"></a>  CDaoException::m_scode

Содержит значение типа `SCODE` , описывающая ошибку.

### <a name="remarks"></a>Примечания

Это кодом OLE. Редко необходимо будет использовать это значение, поскольку почти во всех случаях более подробных сведений об ошибке MFC или DAO доступна в другом `CDaoException` данные-члены.

Сведения о SCODE, см. в разделе [структура OLE кодов ошибок](/windows/desktop/com/structure-of-com-error-codes) в пакете Windows SDK. Тип данных SCODE сопоставляется тип данных значения HRESULT.

## <a name="see-also"></a>См. также

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
