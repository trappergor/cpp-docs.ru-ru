---
title: Класс CDaoException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
dev_langs:
- C++
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4531d63ff7047881f20368cbeaf8e5de4136bb9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369220"
---
# <a name="cdaoexception-class"></a>Класс CDaoException
Представляет условие исключения, поступающее от классов базы данных MFC на базе объектов доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|Создает объект `CDaoException`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoException::GetErrorCount](#geterrorcount)|Возвращает число ошибок в коллекцию ошибок ядра СУБД.|  
|[CDaoException::GetErrorInfo](#geterrorinfo)|Возвращает сведения об ошибке о конкретной ошибке объекте коллекции ошибок.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|Содержит расширенный код ошибки для любой ошибки в классы MFC DAO.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Указатель на [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) , содержащий сведения о один объект ошибки DAO.|  
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode) значение, связанное с ошибкой.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс включает открытые члены данных, используемого для определения причины исключения. `CDaoException` объекты конструирования и создаваемые функции-члены классов баз данных DAO.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классы MFC на основе ODBC; классы на основе DAO доступны данные, включая через драйверы ODBC, через свои собственные компонента database engine. Классы на основе DAO также поддерживают операции языка определения данных (DDL), например добавление таблиц с помощью классов, без необходимости непосредственный вызов DAO. Сведения об исключениях, выдаваемых классами ODBC см. в разделе [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Объекты исключений в пределах доступны [ПЕРЕХВАТЫВАТЬ](../../mfc/reference/exception-processing.md#catch) выражение. Можно также создавать `CDaoException` объектов из кода с [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) глобальной функции.  
  
 В MFC, все ошибки DAO выражаются как исключения типа `CDaoException`. Если происходит перехват исключения этого типа, можно использовать `CDaoException` функции-члены для извлечения сведений из любой ошибки объектов DAO, хранящихся в коллекции ошибок ядра СУБД. Как возникли ошибки, один или несколько объектов ошибки помещаются в коллекцию ошибок. (Обычно коллекция содержит только один объект ошибки; при использовании источника данных ODBC, вы, скорее всего, для получения нескольких объектов ошибок). Если другая операция DAO создает ошибку, в коллекцию ошибок снят, а новый объект ошибки помещается в коллекцию ошибок. DAO операций, которые не создают ошибки не оказывают влияния на коллекцию ошибок.  
  
 Коды ошибок, DAO см. в файле DAOERR. З. Дополнительные сведения см. в разделе «Перехватываемая ошибками доступа к данным» в справке DAO.  
  
 Дополнительные сведения об обработке исключений в общие или о `CDaoException` объектов, см. в статьях [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md). Второй статье содержится пример кода, демонстрируется обработка исключений в DAO.  
  
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
 Как правило платформа создает объекты исключений при его код вызывает исключение. Редко требуется явно создавать объект исключения. Если вы хотите создавать `CDaoException` из кода, вызовите глобальную функцию [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).  
  
 Тем не менее можно явно создавать объект исключения при внесении посредством указателей интерфейса DAO, которые инкапсулируют классы MFC DAO прямые вызовы. В этом случае необходимо получить сведения об ошибке из DAO. Предположим, что при вызове метода DAO в интерфейсе DAODatabases коллекцию баз данных рабочей области в DAO возникает ошибка.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>Для получения сведений об ошибке DAO  
  
1.  Создать `CDaoException` объекта.  
  
2.  Вызвать объект исключения [GetErrorCount](#geterrorcount) функцию-член, чтобы определить, сколько объектов ошибок в коллекцию ошибок ядра СУБД. (Обычно и только если вы не используете источник данных ODBC.)  
  
3.  Вызвать объект исключения [GetErrorInfo](#geterrorinfo) функции-члена для получения одного объекта ошибки во время, по индексу в коллекции, с помощью объекта исключения. Объект исключения можно рассматривать как прокси для одного объекта ошибки DAO.  
  
4.  Проверить текущий [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуру, в которой `GetErrorInfo` возвращает в [m_pErrorInfo](#m_perrorinfo) члена данных. Ее члены содержат сведения об этой ошибке DAO.  
  
5.  В случае использования источника данных ODBC повторите шаги 3 и 4 при необходимости для нескольких объектов ошибок.  
  
6.  Если создан объект исключения в куче, удалите его с **удалить** оператора после завершения.  
  
 Дополнительные сведения об обработке ошибок в классы MFC DAO см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="geterrorcount"></a>  CDaoException::GetErrorCount  
 Вызовите эту функцию-член для извлечения нескольких объектов DAO ошибок в коллекцию ошибок ядра СУБД.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество объектов DAO ошибок в коллекцию ошибок ядра СУБД.  
  
### <a name="remarks"></a>Примечания  
 Эта информация полезна для перебора в коллекцию ошибок для получения всех один или несколько объектов ошибка DAO в коллекции. Чтобы получить объект error по индексу или по номеру ошибки DAO, вызовите [GetErrorInfo](#geterrorinfo) функции-члена.  
  
> [!NOTE]
>  Обычно имеется только один объект ошибки в коллекцию ошибок. При работе с источником данных ODBC, однако может существовать более одного.  
  
##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo  
 Возвращает сведения об ошибке о конкретной ошибке объекте коллекции ошибок.  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс сведения об ошибке в коллекцию ошибок ядра СУБД, для поиска по индексу.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, чтобы получить следующую информацию об исключении:  
  
-   Код ошибки  
  
-   Исходный код  
  
-   Описание  
  
-   Файл справки  
  
-   Контекст справки  
  
 `GetErrorInfo` Эти сведения хранятся в объект исключения `m_pErrorInfo` члена данных. Краткое описание сведений, возвращаемых в разделе [m_pErrorInfo](#m_perrorinfo). Если происходит перехват исключения типа `CDaoException` выводится MFC, `m_pErrorInfo` член уже будет заполнено. Если вы решили вызов DAO напрямую, необходимо вызвать объект исключения `GetErrorInfo` функции-члена самостоятельно заполнить `m_pErrorInfo`. Более подробное описание см. в разделе [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуры.  
  
 Сведения об исключениях DAO и пример кода см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError  
 Содержит MFC расширенный код ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот код содержится в случаях, где неправильного задания определенного компонента классы MFC DAO.  
  
 Доступны следующие значения:  
  
- **NO_AFX_DAO_ERROR** последней операции не привел к MFC расширенное сообщение об ошибке. Тем не менее, операция может выдали другие ошибки из DAO и OLE, поэтому следует выполнять проверку [m_pErrorInfo](#m_perrorinfo) и, возможно, [m_scode](#m_scode).  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC не удается инициализировать ядро базы данных Microsoft Jet. OLE произошел сбой инициализации, или было бы невозможно создать экземпляр объекта ядра базы данных DAO. Эти проблемы обычно предлагают неправильная установка DAO или OLE.  
  
- **AFX_DAO_ERROR_DFX_BIND** адрес, который используется в вызове функции DAO (DFX) exchange поле записи не существует или является недопустимым (адрес не использовался для привязки данных). Неправильный адрес может передано в вызове DFX или адрес может оказаться недопустимым между операциями DFX.  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN** предпринята попытка открыть набор записей, на основе querydef или tabledef объект, который не находилось в открытом состоянии.  
  
##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo  
 Содержит указатель на `CDaoErrorInfo` структуру, которая предоставляет сведения о объект error DAO, последнего полученного посредством обращения [GetErrorInfo](#geterrorinfo).  
  
### <a name="remarks"></a>Примечания  
 Этот объект содержит следующие сведения:  
  
|CDaoErrorInfo-член|Сведения|Значение|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|Код ошибки|Код ошибки DAO|  
|`m_strSource`|Исходный код|Имя объекта или приложения, вызвавшего ошибку|  
|`m_strDescription`|Описание|Строку описания, связанный с ошибкой|  
|`m_strHelpFile`|Файл справки|Путь к файлу справки Windows, в котором пользователь может получить сведения о данной проблеме|  
|**m_lHelpContext**|Контекст справки|Идентификатор контекста для раздела в файле справки DAO|  
  
 Полные сведения об информации, содержащейся в `CDaoErrorInfo` см. в разделе [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуры.  
  
##  <a name="m_scode"></a>  CDaoException::m_scode  
 Содержит значение типа `SCODE` , описывающая ошибку.  
  
### <a name="remarks"></a>Примечания  
 Это код OLE. Редко необходимо будет использовать это значение, так как в большинстве случаев более конкретные сведения об ошибке MFC или DAO доступен в других `CDaoException` членов данных.  
  
 Сведения о `SCODE`, см. в разделе [структура OLE кодов ошибок](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK. `SCODE` Сопоставляется с типом данных `HRESULT` типа данных.  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CException](../../mfc/reference/cexception-class.md)
