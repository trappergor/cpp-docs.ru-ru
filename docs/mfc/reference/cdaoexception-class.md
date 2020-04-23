---
title: Класс CDaoException
ms.date: 09/17/2019
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
ms.openlocfilehash: 935d7870d68554d702e2ad762e83343cb518b2b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754728"
---
# <a name="cdaoexception-class"></a>Класс CDaoException

Представляет условие исключения, поступающее от классов базы данных MFC на базе объектов доступа к данным (DAO). DAO 3.6 является окончательной версией, и он считается устаревшим.

## <a name="syntax"></a>Синтаксис

```
class CDaoException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDao Исключение::CDaoException](#cdaoexception)|Формирует объект `CDaoException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoException::GetErrorCount](#geterrorcount)|Возвращает количество ошибок в сборе ошибок движка базы данных.|
|[CDao Исключение::GetErrorInfo](#geterrorinfo)|Возвращает информацию об ошибке конкретного объекта ошибки в коллекции Ошибок.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDao Исключение::m_nAfxDaoError](#m_nafxdaoerror)|Содержит расширенный код ошибки для любой ошибки в классах MFC DAO.|
|[CDaoИсключение::m_pErrorInfo](#m_perrorinfo)|Указатель на объект [CDaoErrorInfo,](../../mfc/reference/cdaoerrorinfo-structure.md) содержащий информацию об одном объекте ошибки DAO.|
|[CDaoИсключение::m_scode](#m_scode)|Значение [SCODE,](#m_scode) связанное с ошибкой.|

## <a name="remarks"></a>Remarks

Класс включает в себя открытых членов данных, которые можно использовать для определения причины исключения. `CDaoException`объекты строятся и выбрасываются функциями членов классов баз данных DAO.

> [!NOTE]
> Классы баз данных DAO отличаются от классов баз данных MFC на основе open Database Connectivity (ODBC). Все названия классов баз данных DAO имеют префикс "CDao". Вы все еще можете получить доступ к источникам данных ODBC с классами DAO. В целом, классы МФЦ на основе DAO более способны, чем классы МФЦ на основе ODBC; классы на базе DAO могут получать доступ к данным, в том числе через драйверы ODBC, через свой собственный движок баз данных. Классы, основанные на DAO, также поддерживают операции языка определения данных (DDL), такие как добавление таблиц через классы, без прямого вызова DAO. Для получения информации об исключениях, брошенных классами ODBC, [см.](../../mfc/reference/cdbexception-class.md)

Можно получить доступ к объектам исключений в рамках выражения [CATCH.](../../mfc/reference/exception-processing.md#catch) Вы также `CDaoException` можете бросать объекты из собственного кода с глобальной функцией [AfxThrowDaoException.](../../mfc/reference/exception-processing.md#afxthrowdaoexception)

В МФЦ все ошибки DAO выражаются `CDaoException`как исключения типа. При поимке исключения этого типа `CDaoException` можно использовать функции членов для получения информации из любых объектов ошибок DAO, хранящихся в коллекции ошибок движка базы данных. По мере каждой ошибки в коллекции Ошибок помещается один или несколько объектов ошибок. (Обычно коллекция содержит только один объект ошибки; если вы используете источник данных ODBC, вы с большей вероятностью получите несколько объектов ошибки.) Когда другая операция DAO генерирует ошибку, сбор ошибок очищается, а новый объект ошибки помещается в коллекцию Ошибок. Операции DAO, не генерирующие ошибку, не влияют на сбор ошибок.

Для кодов ошибок DAO см. H. Для получения соответствующей информации смотрите тему "Ошибки доступа к данным" в справке DAO.

Для получения дополнительной информации об `CDaoException` обработке исключений в целом или [Exceptions: Database Exceptions](../../mfc/exceptions-database-exceptions.md)об объектах см. [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md) Вторая статья содержит пример кода, иллюстрирующего обработку исключений в DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>CDao Исключение::CDaoException

Формирует объект `CDaoException`.

```
CDaoException();
```

### <a name="remarks"></a>Remarks

Обычно фреймворк создает объекты исключений, когда код бросает исключение. Редко требуется построить объект исключения явно. Если вы хотите `CDaoException` выбросить из собственного кода, позвоните в глобальную функцию [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).

Тем не менее, вы можете явно создать объект исключения, если вы делаете прямые звонки в DAO через указатели интерфейса DAO, которые инкапсулируют классы MFC. В этом случае может потребоваться получение информации об ошибках из DAO. Предположим, что ошибка возникает в DAO при вызове метода DAO через интерфейс DAODatabases в коллекцию баз данных рабочего пространства.

##### <a name="to-retrieve-the-dao-error-information"></a>Для получения информации об ошибках DAO

1. Постройте `CDaoException` объект.

1. Позвоните в функцию участника [GetErrorCount](#geterrorcount) объекта исключения, чтобы определить, сколько объектов ошибок находятся в коллекции ошибок движка базы данных. (Обычно только один, если вы используете источник данных ODBC.)

1. Позвоните в функцию участника [GetErrorInfo](#geterrorinfo) объекта исключения, чтобы получить один конкретный объект ошибки за раз, по индексу в коллекции, через объект исключения. Думайте об объекте исключения как о прокси для одного объекта ошибки DAO.

1. Изучите текущую структуру [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)`GetErrorInfo`, которая возвращает элемент данных [m_pErrorInfo](#m_perrorinfo) . Его члены предоставляют информацию об ошибке DAO.

1. В случае источника данных ODBC повторите шаги 3 и 4 по мере необходимости для большего количества объектов ошибок.

1. Если объект исключения построен на куче, удалите его с помощью оператора **удаления,** когда вы закончите.

Для получения дополнительной информации об ошибках обработки в [Exceptions: Database Exceptions](../../mfc/exceptions-database-exceptions.md)классах MFC DAO см.

## <a name="cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>CDao Исключение::GetErrorCount

Вызовите эту функцию участника, чтобы получить количество объектов ошибок DAO в коллекции ошибок движка базы данных.

```
short GetErrorCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество объектов ошибок DAO в коллекции ошибок движка базы данных.

### <a name="remarks"></a>Remarks

Эта информация полезна для цикла коллекции Ошибок для извлечения каждого из одного или нескольких объектов ошибки DAO в коллекции. Чтобы получить объект ошибки по индексу или номеру ошибки DAO, позвоните в функцию участника [GetErrorInfo.](#geterrorinfo)

> [!NOTE]
> Обычно в коллекции Ошибок есть только один объект ошибки. Если вы работаете с источником данных ODBC, однако, может быть несколько.

## <a name="cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>CDao Исключение::GetErrorInfo

Возвращает информацию об ошибке конкретного объекта ошибки в коллекции Ошибок.

```cpp
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс информации об ошибке в сборе ошибок движка базы данных для поиска по индексу.

### <a name="remarks"></a>Remarks

Позвоните в эту функцию участника, чтобы получить следующие виды информации об исключении:

- Код ошибки

- Источник

- Описание

- Файл справки

- Контекст справки

`GetErrorInfo`хранит информацию в составе `m_pErrorInfo` объекта исключения. Краткое описание возвращенной информации см [m_pErrorInfo.](#m_perrorinfo) Если вы поймаете `CDaoException` исключение типа, `m_pErrorInfo` брошенного MFC, участник уже будет заполнен. Если вы решите позвонить в DAO напрямую, вы должны позвонить `GetErrorInfo` функции члена объекта исключения самостоятельно, чтобы заполнить. `m_pErrorInfo` Более подробное описание можно получить в структуре [CDaoErrorInfo.](../../mfc/reference/cdaoerrorinfo-structure.md)

Для получения информации об исключениях DAO [Exceptions: Database Exceptions](../../mfc/exceptions-database-exceptions.md)и примере кода см.

## <a name="cdaoexceptionm_nafxdaoerror"></a><a name="m_nafxdaoerror"></a>CDao Исключение::m_nAfxDaoError

Содержит расширенный код ошибки MFC.

### <a name="remarks"></a>Remarks

Этот код поставляется в тех случаях, когда определенный компонент классов DAO MFC допустил добой.

Возможны следующие значения:

- NO_AFX_DAO_ERROR Последняя операция не привела к ошибке расширенной МФЦ. Тем не менее, операция могла бы привести к другим ошибкам от DAO или OLE, так что вы должны проверить [m_pErrorInfo](#m_perrorinfo) и, возможно, [m_scode](#m_scode).

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC не смогла инициализировать движок базы данных Microsoft Jet. ВОЗМОЖНО, OL не удалось инициализировать, или, возможно, было невозможно создать экземпляр объекта движка базы данных DAO. Эти проблемы обычно предполагают плохую установку либо DAO или OLE.

- AFX_DAO_ERROR_DFX_BIND адрес, используемый в вызове функции обмена поля записи DAO (DFX) не существует или является недействительным (адрес не использовался для связывания данных). Возможно, вы прошли плохой адрес в вызове DFX, или адрес может стать недействительным между операциями DFX.

- AFX_DAO_ERROR_OBJECT_NOT_OPEN Вы пытались открыть набор записей на основе объекта querydef или таблицы, который не находился в открытом состоянии.

## <a name="cdaoexceptionm_perrorinfo"></a><a name="m_perrorinfo"></a>CDaoИсключение::m_pErrorInfo

Содержит указатель на `CDaoErrorInfo` структуру, которая предоставляет информацию об объекте ошибки DAO, который вы в последний раз извлекли, позвонив [в GetErrorInfo.](#geterrorinfo)

### <a name="remarks"></a>Remarks

Этот объект содержит следующую информацию:

|Член CDaoErrorInfo|Сведения|Значение|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|Код ошибки|Код ошибки DAO|
|`m_strSource`|Источник|Имя объекта или приложения, первоначально сгенерированного поошибкой|
|`m_strDescription`|Описание|Описательная строка, связанная с ошибкой|
|`m_strHelpFile`|Файл справки|Путь к файлу справки Windows, в котором пользователь может получить информацию о проблеме|
|`m_lHelpContext`|Справка Контекст|Идентификатор контекста для темы в файле справки DAO|

Подробную информацию об информации, содержащейся в `CDaoErrorInfo` объекте, можно получить в структуре [CDaoErrorInfo.](../../mfc/reference/cdaoerrorinfo-structure.md)

## <a name="cdaoexceptionm_scode"></a><a name="m_scode"></a>CDaoИсключение::m_scode

Содержит значение типа, `SCODE` описывающий ошибку.

### <a name="remarks"></a>Remarks

Это код OLE. Вам редко придется использовать это значение, потому что почти во всех случаях более конкретная `CDaoException` информация об ошибках MFC или DAO доступна в других членах данных.

Для получения информации о SCODE, [см.](/windows/win32/com/structure-of-com-error-codes) Карты типа данных SCODE к типу данных HRESULT.

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
