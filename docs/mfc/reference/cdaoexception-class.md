---
title: "Класс CDaoException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- errors [C++], DAO
- CDaoException class
- DAO (Data Access Objects), exceptions
- exceptions, in MFC DAO classes
- Errors collection, DAO
- collections, DAO errors
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d1cb1c6dbe50d383981af03cc97d1977be12a5f6
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoexception-class"></a>Класс CDaoException
Представляет условие исключения, поступающее от классов базы данных MFC на базе объектов доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|Создает объект `CDaoException`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoException::GetErrorCount](#geterrorcount)|Возвращает число ошибок в коллекции ошибки ядра СУБД.|  
|[CDaoException::GetErrorInfo](#geterrorinfo)|Возвращает сведения об объекте конкретной ошибки в коллекцию ошибок.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|Содержит расширенный код ошибки для ошибки в классах MFC DAO.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Указатель на [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) , содержащий сведения о один объект error DAO.|  
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode) значение, связанное с ошибкой.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс включает открытые члены данных, можно использовать, чтобы определить причину исключения. `CDaoException`объекты конструирования и создаваемые функции-члены классов баз данных DAO.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Можно по-прежнему обращаться к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классов MFC на основе ODBC; классы на основе DAO доступны данные, включая посредством драйверов ODBC, через свои собственные компонента database engine. Классы на основе DAO также поддерживают операции языка определения данных (DDL), например добавление таблиц с помощью классов, без непосредственного вызова DAO. Сведения о исключения, создаваемые классы ODBC см [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Можно использовать объекты исключение в области [CATCH](../../mfc/reference/exception-processing.md#catch) выражение. Можно также создавать `CDaoException` объектов из кода с помощью [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) глобальной функции.  
  
 В MFC, все ошибки DAO выражаются в виде исключения типа `CDaoException`. Если происходит перехват исключения этого типа, можно использовать `CDaoException` функции-члены для извлечения информации из любой DAO ошибки, хранящихся в коллекции ошибки ядра СУБД. При возникновении каждой ошибки один или несколько объектов ошибок, помещаются в коллекцию ошибок. (Обычно коллекция содержит только один объект ошибки, при использовании источника данных ODBC, скорее всего для получения нескольких объектов ошибок). Если другая операция DAO создает ошибку, Коллекция ошибок снят, а новый объект ошибки помещается в коллекцию ошибок. DAO операций, которые не создаст ошибку не оказывают влияния на коллекцию ошибок.  
  
 Коды ошибок, DAO см. в файле DAOERR. З. Дополнительные сведения см. в разделе «Перехватываемая ошибками доступа к данным» в справке DAO.  
  
 Дополнительные сведения об обработке исключений в общие или о `CDaoException` объектов, см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md). Во второй статье содержится пример кода, иллюстрирующий обработки исключений в DAO.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="cdaoexception"></a>CDaoException::CDaoException  
 Создает объект `CDaoException`.  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>Примечания  
 Как правило платформа создает объекты исключений при его код выдает исключение. Редко требуется явно создавать объект исключения. Если вы хотите вызвать `CDaoException` из кода, вызовите глобальную функцию [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).  
  
 Тем не менее требуется явно создавать объект исключения при создании через указатели интерфейса DAO, которые инкапсулируют классы MFC DAO прямые вызовы. В этом случае необходимо получить сведения об ошибке из DAO. Предположим, что при вызове метода DAO через интерфейс DAODatabases коллекцию рабочей базы данных в DAO возникает ошибка.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>Для получения сведений об ошибке DAO  
  
1.  Создать `CDaoException` объекта.  
  
2.  Вызвать объект исключения [GetErrorCount](#geterrorcount) функцию-член, чтобы определить, сколько объектов ошибок в коллекцию ошибок ядра СУБД. (Обычно только один только при использовании источника данных ODBC.)  
  
3.  Вызвать объект исключения [GetErrorInfo](#geterrorinfo) функции-члена для извлечения одного объекта ошибки одновременно, по индексу в коллекции, с помощью объекта исключения. Объект исключения можно рассматривать как прокси для одного объекта ошибки DAO.  
  
4.  Рассмотрим существующие [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуру, в которой `GetErrorInfo` возвращает [m_pErrorInfo](#m_perrorinfo) данные-член. Ее члены содержат сведения об этой ошибке DAO.  
  
5.  В случае источник данных ODBC повторите шаги 3 и 4, необходимые для нескольких объектов ошибок.  
  
6.  Если созданный объект исключения в куче, удалите его с **удаление** оператора после завершения.  
  
 Дополнительные сведения об обработке ошибок в классах MFC DAO см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="geterrorcount"></a>CDaoException::GetErrorCount  
 Вызовите эту функцию-член для получения числа объектов DAO ошибок в коллекцию ошибок ядра СУБД.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество объектов DAO ошибок в коллекцию ошибок ядра СУБД.  
  
### <a name="remarks"></a>Примечания  
 Эта информация полезна для перебора коллекции ошибок для получения всех один или несколько объектов ошибок DAO в коллекции. Чтобы получить объект error по индексу или по номеру ошибки DAO, вызовите [GetErrorInfo](#geterrorinfo) функции-члена.  
  
> [!NOTE]
>  Обычно существует только один объект error в коллекцию ошибок. При работе с источником данных ODBC, однако может существовать более одного.  
  
##  <a name="geterrorinfo"></a>CDaoException::GetErrorInfo  
 Возвращает сведения об объекте конкретной ошибки в коллекцию ошибок.  
  
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
  
 `GetErrorInfo`Эти сведения хранятся в объект исключения `m_pErrorInfo` члена данных. Краткое описание сведений, возвращаемых в разделе [m_pErrorInfo](#m_perrorinfo). Если происходит перехват исключения типа `CDaoException` выводится MFC, `m_pErrorInfo` члена будут уже заполнены. При выборе для прямого вызова DAO необходимо вызвать объект исключения `GetErrorInfo` функции-члена самостоятельно заполнить `m_pErrorInfo`. Более подробное описание см. в разделе [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуры.  
  
 Сведения об исключениях DAO и пример кода см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="m_nafxdaoerror"></a>CDaoException::m_nAfxDaoError  
 Содержит MFC расширенный код ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот код предоставляется в случаях, где неправильного задания определенный компонент классы MFC DAO.  
  
 Доступны следующие значения:  
  
- **NO_AFX_DAO_ERROR** последней операции не привел к MFC расширенное сообщение об ошибке. Тем не менее, операция может выдали других ошибок DAO или OLE, поэтому следует проверить [m_pErrorInfo](#m_perrorinfo) и, возможно, [m_scode](#m_scode).  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC не удается инициализировать ядро базы данных Microsoft Jet. OLE может не удалось инициализировать или было бы невозможно создать экземпляр объекта ядра базы данных DAO. Эти проблемы обычно предлагают неправильная установка DAO или OLE.  
  
- **AFX_DAO_ERROR_DFX_BIND** адрес, который используется в вызове функции DAO (DFX) exchange поле записи не существует или является недопустимым (адрес не использовался для привязки данных). Неверный адрес может передается в вызов DFX или адрес может оказаться недопустимым между операциями DFX.  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN** попытка открыть набор записей на основе querydef или tabledef объект, который не был в открытом состоянии.  
  
##  <a name="m_perrorinfo"></a>CDaoException::m_pErrorInfo  
 Содержит указатель на `CDaoErrorInfo` структура, которая предоставляет сведения о DAO объекта ошибки, вы извлекли путем вызова [GetErrorInfo](#geterrorinfo).  
  
### <a name="remarks"></a>Примечания  
 Этот объект содержит следующие сведения:  
  
|Член CDaoErrorInfo|Сведения|Значение|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|Код ошибки|Код ошибки DAO|  
|`m_strSource`|Исходный код|Имя объекта или приложения, вызвавшего ошибку|  
|`m_strDescription`|Описание|Строку описания, связанного с ошибкой.|  
|`m_strHelpFile`|Файл справки|Путь для файла справки Windows, в котором пользователь может получить сведения о проблеме|  
|**m_lHelpContext**|Контекст справки|Идентификатор контекста для раздела в файле справки DAO|  
  
 Дополнительные сведения об информации, содержащейся в `CDaoErrorInfo` объекта см. в разделе [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) структуры.  
  
##  <a name="m_scode"></a>CDaoException::m_scode  
 Содержит значение типа `SCODE` , описывающая ошибку.  
  
### <a name="remarks"></a>Примечания  
 Это код OLE. Редко требуется использовать это значение, поскольку почти во всех случаях более конкретные сведения об ошибках MFC или DAO доступна в другом `CDaoException` члены данных.  
  
 Сведения о `SCODE`, см. в разделе [структура объекта OLE коды ошибок](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `SCODE` Тип данных сопоставляется `HRESULT` тип данных.  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)

