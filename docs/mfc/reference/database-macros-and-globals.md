---
title: Макросы и глобальные объекты баз данных
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 4e9700311bbc20ea017675357a91a56813cc4bde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376964"
---
# <a name="database-macros-and-globals"></a>Макросы и глобальные объекты баз данных

Макросы и глобальные данные, перечисленные ниже, применяются к приложениям баз данных на основе ODBC. Они не используются с приложениями на основе DAO.

Перед MFC 4.2, `AFX_SQL_ASYNC` макросы и `AFX_SQL_SYNC` дал асинхронные операции возможность уступить время другим процессам. Начиная с MFC 4.2, реализация этих макросов изменилась, поскольку классы MFC ODBC использовали только синхронные операции. Макрос `AFX_ODBC_CALL` был новым для MFC 4.2.

### <a name="database-macros"></a>Макрос базы данных

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Вызывает функцию ODBC API, которая возвращается. `SQL_STILL_EXECUTING` `AFX_ODBC_CALL`будет неоднократно вызывать функцию, `SQL_STILL_EXECUTING`пока она больше не возвращается.|
|[AFX_SQL_ASYNC](#afx_sql_async)|Вызывает `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Вызывает функцию ODBC API, `SQL_STILL_EXECUTING`которая не возвращается.|

### <a name="database-globals"></a>База данных Globals

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|Добавляет поддержку базы данных для регулярного MFC DLL, который динамически связан с MFC.|
|[AfxGetHENV](#afxgethenv)|Извлекает ручку в среду ODBC, используемую в настоящее время MFC. Вы можете использовать эту ручку при прямых вызовах ODBC.|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a>AfxDbInitModule

Для поддержки базы данных MFC (или DAO) от регулярного MFC DLL, который динамически связан с `CWinApp::InitInstance` MFC, добавьте вызов к этой функции в вашей обычной функции MFC DLL для инициализации базы данных MFC DLL.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Remarks

Убедитесь, что этот вызов происходит до любого вызова базового класса или любого дополнительного кода, который получает доступ к базе данных MFC DLL. База данных MFC DLL является расширением MFC DLL; для того, чтобы расширение MFC DLL `CDynLinkLibrary` попало в цепочку, оно должно создать `CDynLinkLibrary` объект в контексте каждого модуля, который будет его использовать. `AfxDbInitModule`создает `CDynLinkLibrary` объект в контексте вашего обычного MFC DLL, `CDynLinkLibrary` чтобы он попал в цепочку объектов обычного MFC DLL.

### <a name="requirements"></a>Требования

**Заголовок:** \<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a>AFX_ODBC_CALL

Используйте этот макрос для вызова любой `SQL_STILL_EXECUTING`функции ODBC API, которая может вернуться.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Параметры

*СЗЛФунк*<br/>
Функция API ODBC. Для получения дополнительной информации о функциях ODBC API см.

### <a name="remarks"></a>Remarks

`AFX_ODBC_CALL`неоднократно вызывает функцию, пока `SQL_STILL_EXECUTING`она больше не возвращается.

Прежде чем `AFX_ODBC_CALL`ссылаться, вы должны `nRetCode`объявить переменную, типа RETCODE.

Обратите внимание, что в классах MFC ODBC теперь используется только синхронная обработка. Для выполнения асинхронной операции необходимо позвонить в функцию `SQLSetConnectOption`ODBC API. Для получения дополнительной информации, см.

### <a name="example"></a>Пример

Этот пример `AFX_ODBC_CALL` используется `SQLColumns` для вызова функции API ODBC, которая возвращает список столбцов в таблице, названной по номеру `strTableName` Обратите внимание `nRetCode` на объявление и использование членов данных, установленных записью, для передачи параметров функции. Пример также иллюстрирует проверку результатов `Check`вызова с функцией `CRecordset`участника класса. Переменная `prs` является указателем `CRecordset` на объект, объявленный в другом месте.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a>AFX_SQL_ASYNC

Реализация этого макроса изменилась в МФЦ 4.2.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Параметры

*Prs*<br/>
Указатель на `CRecordset` объект или `CDatabase` объект. Начиная с MFC 4.2, это значение параметра игнорируется.

*СЗЛФунк*<br/>
Функция API ODBC. Для получения дополнительной информации о функциях ODBC API см.

### <a name="remarks"></a>Remarks

`AFX_SQL_ASYNC`просто вызывает [макроAFX_ODBC_CALL](#afx_odbc_call) и игнорирует параметр *prs.* В версиях MFC до 4.2, `AFX_SQL_ASYNC` был использован для вызова `SQL_STILL_EXECUTING`функций ODBC API, которые могут вернуться. Если функция ODBC API `SQL_STILL_EXECUTING`действительно `AFX_SQL_ASYNC` возвращается, то вызов. `prs->OnWaitForDataSource`

> [!NOTE]
> В классах MFC ODBC теперь используется только синхронная обработка. Для выполнения асинхронной операции необходимо позвонить в функцию `SQLSetConnectOption`ODBC API. Для получения дополнительной информации, см.

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a>AFX_SQL_SYNC

Макрос `AFX_SQL_SYNC` просто вызывает `SQLFunc`функцию.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Параметры

*СЗЛФунк*<br/>
Функция API ODBC. Для получения дополнительной информации об этих функциях см.

### <a name="remarks"></a>Remarks

Используйте этот макрос для вызова функций `SQL_STILL_EXECUTING`ODBC API, которые не будут возвращаться.

Перед `AFX_SQL_SYNC`вызовом, вы должны `nRetCode`объявить переменную, типа RETCODE. Вы можете проверить `nRetCode` значение после макровызова.

Обратите внимание, `AFX_SQL_SYNC` что реализация изменена в МФЦ 4.2. Поскольку проверка состояния сервера `AFX_SQL_SYNC` больше не требуется, просто присваивает `nRetCode`значение. Например, вместо того, чтобы звонить

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

Вы можете просто сделать задание

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

## <a name="afxgethenv"></a><a name="afxgethenv"></a>AfxGetHENV

Вы можете использовать возвращенную ручку при прямых вызовах ODBC, но вы не должны `CDatabase`закрывать `CRecordset`ручку или предполагать, что ручка по-прежнему действительна и доступна после того, как любые существующие или полученные объекты были уничтожены.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к среде ODBC в настоящее время используется MFC. Может `SQL_HENV_NULL` быть, если Есть нет [объектов CDatabase](../../mfc/reference/cdatabase-class.md) и нет [CRecordset](../../mfc/reference/crecordset-class.md) объектов в использовании.

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
