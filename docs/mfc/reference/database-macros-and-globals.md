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
ms.openlocfilehash: 47a1bb434801c24ab8eee048d9ef8f93793101cc
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426273"
---
# <a name="database-macros-and-globals"></a>Макросы и глобальные объекты баз данных

Указанные ниже макросы и глобальные приложения применимы к приложениям баз данных на основе ODBC. Они не используются в приложениях на основе DAO.

До MFC 4,2 макросы `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` предоставили асинхронным операциям возможность выдавать время другим процессам. Начиная с MFC 4,2, реализация этих макросов изменилась, так как классы ODBC MFC используют только синхронные операции. Макрос `AFX_ODBC_CALL` был впервые добавлен в MFC 4,2.

### <a name="database-macros"></a>Макросы базы данных

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Вызывает функцию API ODBC, которая возвращает `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL` будет вызывать функцию повторно, пока она больше не возвратит `SQL_STILL_EXECUTING`.|
|[AFX_SQL_ASYNC](#afx_sql_async)|Вызывает `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Вызывает функцию API ODBC, которая не возвращает `SQL_STILL_EXECUTING`.|

### <a name="database-globals"></a>Глобальные базы данных

|||
|-|-|
|[афксдбинитмодуле](#afxdbinitmodule)|Добавляет поддержку базы данных для обычной библиотеки DLL MFC, которая динамически связана с MFC.|
|[афксжесенв](#afxgethenv)|Извлекает маркер среды ODBC, используемой в настоящий момент библиотекой MFC. Этот обработчик можно использовать в прямых вызовах ODBC.|

## <a name="afxdbinitmodule"></a>афксдбинитмодуле

Для поддержки базы данных MFC (или DAO) из обычной библиотеки DLL MFC, которая динамически связана с MFC, добавьте вызов этой функции в функции `CWinApp::InitInstance` в обычной библиотеке DLL MFC для инициализации библиотеки DLL базы данных MFC.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Remarks

Убедитесь, что этот вызов происходит до любого вызова базового класса или любого добавленного кода, который обращается к библиотеке DLL базы данных MFC. Библиотека DLL базы данных MFC является библиотекой DLL расширения MFC. чтобы библиотека DLL расширения MFC была подключена к цепочке `CDynLinkLibrary`, она должна создать объект `CDynLinkLibrary` в контексте каждого модуля, который будет его использовать. `AfxDbInitModule` создает объект `CDynLinkLibrary` в контексте обычной библиотеки DLL MFC, чтобы он был подключен в `CDynLinkLibrary` цепочки объектов обычной библиотеки DLL MFC.

### <a name="requirements"></a>Требования

**Заголовок:** \<AFXDLL_. h >

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL

Используйте этот макрос для вызова любой функции API ODBC, которая может возвращать `SQL_STILL_EXECUTING`.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Параметры

*склфунк*<br/>
Функция API ODBC. Дополнительные сведения о функциях API ODBC см. в Windows SDK.

### <a name="remarks"></a>Remarks

`AFX_ODBC_CALL` повторно вызывает функцию, пока она больше не возвращает `SQL_STILL_EXECUTING`.

Перед вызовом `AFX_ODBC_CALL`необходимо объявить переменную `nRetCode`типа РЕТКОДЕ.

Обратите внимание, что классы ODBC MFC теперь используют только синхронную обработку. Чтобы выполнить асинхронную операцию, необходимо вызвать функцию API ODBC `SQLSetConnectOption`. Дополнительные сведения см. в разделе "асинхронное выполнение функций в Windows SDK".

### <a name="example"></a>Пример

В этом примере используется `AFX_ODBC_CALL` для вызова функции `SQLColumns` ODBC API, которая возвращает список столбцов в таблице с именем, равным `strTableName`. Обратите внимание на объявление `nRetCode` и использование элементов данных набора записей для передачи параметров в функцию. В примере также показано, как проверить результаты вызова с помощью `Check`, функции-члена класса `CRecordset`. Переменная `prs` является указателем на объект `CRecordset`, объявленный в других местах.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** афксдб. h

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC

Реализация этого макроса изменена в MFC 4,2.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Параметры

*Вытягивание*<br/>
Указатель на `CRecordset` объект или объект `CDatabase`. Начиная с MFC 4,2, значение этого параметра игнорируется.

*склфунк*<br/>
Функция API ODBC. Дополнительные сведения о функциях API ODBC см. в Windows SDK.

### <a name="remarks"></a>Remarks

`AFX_SQL_ASYNC` просто вызывает макрос [AFX_ODBC_CALL](#afx_odbc_call) и игнорирует параметр *вытягивание* . В версиях MFC до 4,2 `AFX_SQL_ASYNC` использовался для вызова функций API ODBC, которые могут возвращать `SQL_STILL_EXECUTING`. Если функция API ODBC возвратила `SQL_STILL_EXECUTING`, `AFX_SQL_ASYNC` вызовет `prs->OnWaitForDataSource`.

> [!NOTE]
>  Классы ODBC MFC теперь используют только синхронную обработку. Чтобы выполнить асинхронную операцию, необходимо вызвать функцию API ODBC `SQLSetConnectOption`. Дополнительные сведения см. в разделе "асинхронное выполнение функций в Windows SDK".

### <a name="requirements"></a>Требования

  **Заголовок** афксдб. h

##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC

Макрос `AFX_SQL_SYNC` просто вызывает функцию `SQLFunc`.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Параметры

*склфунк*<br/>
Функция API ODBC. Дополнительные сведения об этих функциях см. в Windows SDK.

### <a name="remarks"></a>Remarks

Используйте этот макрос для вызова функций API ODBC, которые не будут возвращать `SQL_STILL_EXECUTING`.

Перед вызовом `AFX_SQL_SYNC`необходимо объявить переменную `nRetCode`типа РЕТКОДЕ. Можно проверить значение `nRetCode` после вызова макроса.

Обратите внимание, что реализация `AFX_SQL_SYNC` изменилась в MFC 4,2. Поскольку проверка состояния сервера больше не требуется, `AFX_SQL_SYNC` просто присваивает значение `nRetCode`. Например, вместо выполнения вызова

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

можно просто сделать назначение

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** афксдб. h

##  <a name="afxgethenv"></a>афксжесенв

Возвращенный обработчик можно использовать в прямых вызовах ODBC, но не следует закрывать этот обработчик или предполагается, что он по-прежнему является допустимым и доступным после уничтожения всех существующих `CDatabase`или `CRecordset`объектов.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик для среды ODBC, используемой в настоящий момент библиотекой MFC. Может быть `SQL_HENV_NULL`, если отсутствуют объекты [CDatabase](../../mfc/reference/cdatabase-class.md) и объекты [CRecordset](../../mfc/reference/crecordset-class.md) не используются.

### <a name="requirements"></a>Требования

  **Заголовок** афксдб. h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
