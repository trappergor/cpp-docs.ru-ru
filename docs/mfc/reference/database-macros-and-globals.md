---
title: "Макросы и глобальные объекты баз данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [C++]
- database macros [C++]
- database globals [C++]
- global functions [C++], database functions
- macros [C++], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9706c47d9bd5996c28873da6a15a687bf9b5e038
ms.lasthandoff: 02/24/2017

---
# <a name="database-macros-and-globals"></a>Макросы и глобальные объекты баз данных
Макросы и глобальные объекты, перечисленные ниже применяются к приложениям баз данных на основе ODBC. Они не используются с приложениями на основе DAO.  
  
 Прежде чем MFC версии 4.2, макросы `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` дает возможность выдавать времени для других процессов асинхронных операций. Начиная с MFC версии 4.2, реализация этих макросов, изменить, так как классы MFC ODBC используется только для синхронных операций. Макрос `AFX_ODBC_CALL` впервые появился в MFC версии 4.2.  
  
### <a name="database-macros"></a>Макросы базы данных  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|Вызывает функцию ODBC API, которая возвращает `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL`будет повторно вызывать функцию до его больше не возвращает `SQL_STILL_EXECUTING`.|  
|[AFX_SQL_ASYNC](#afx_sql_async)|Вызывает `AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|Вызывает функцию ODBC API, не возвращающих `SQL_STILL_EXECUTING`.|  
  
### <a name="database-globals"></a>Глобальные значения базы данных  
  
|||  
|-|-|  
|[AfxGetHENV](#afxgethenv)|Получает дескриптор среды ODBC в настоящий момент каким MFC. Можно использовать этот дескриптор в прямые вызовы ODBC.|  
  
##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 Использовать этот макрос для вызова любой функции API-интерфейса ODBC, могут возвращать `SQL_STILL_EXECUTING`.  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>Параметры  
 `SQLFunc`  
 Функции ODBC API. Дополнительные сведения о функции ODBC API см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 `AFX_ODBC_CALL`несколько раз вызывает функцию до его больше не возвращает `SQL_STILL_EXECUTING`.  
  
 Перед вызовом `AFX_ODBC_CALL`, необходимо объявить переменную, `nRetCode`, типа **RETCODE**.  
  
 Обратите внимание, что MFC ODBC классы теперь использовать только синхронную обработку. Для выполнения асинхронной операции, необходимо вызвать функцию ODBC API **SQLSetConnectOption**. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  

  
### <a name="example"></a>Пример  
 В этом примере используется `AFX_ODBC_CALL` для вызова **SQLColumns** API-функцию ODBC, который возвращает список столбцов в таблице с именем `strTableName`. Обратите внимание на объявление `nRetCode` и использование членов данных набора записей для передачи параметров в функцию. В примере также демонстрируется проверка результатов вызова с **проверки**, функция-член класса `CRecordset`. Переменная `prs` — это указатель на `CRecordset` объект, объявленные в другом месте.  
  
 [!code-cpp[NVC_MFCDatabase&#39;](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 Реализация данного макроса в MFC версии 4.2.  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>Параметры  
 `prs`  
 Указатель на `CRecordset` объекта или `CDatabase` объекта. Начиная с MFC версии 4.2, значение этого параметра учитывается.  
  
 `SQLFunc`  
 Функции ODBC API. Дополнительные сведения о функции ODBC API см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 `AFX_SQL_ASYNC`просто вызывает макрос [AFX_ODBC_CALL](#afx_odbc_call) и игнорирует `prs` параметр. В MFC версии до версии 4.2 `AFX_SQL_ASYNC` использовался для вызова функций ODBC API, которые может вернуть `SQL_STILL_EXECUTING`. Если было получено функцию ODBC API `SQL_STILL_EXECUTING`, затем `AFX_SQL_ASYNC` вызовет `prs->OnWaitForDataSource`.  
  
> [!NOTE]
>  Теперь классы MFC ODBC использовать только синхронную обработку. Для выполнения асинхронной операции, необходимо вызвать функцию ODBC API **SQLSetConnectOption**. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
  
##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC` Макрос просто вызывает функцию `SQLFunc`.  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>Параметры  
 `SQLFunc`  
 Функции ODBC API. Дополнительные сведения об этих функциях см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос для вызова функций ODBC API, которые не вернет `SQL_STILL_EXECUTING`.  
  
 Перед вызовом метода `AFX_SQL_SYNC`, необходимо объявить переменную, `nRetCode`, типа **RETCODE**. Можно проверить значение `nRetCode` после вызова макроса.  
  
 Обратите внимание, что реализация `AFX_SQL_SYNC` изменения в MFC версии 4.2. Поскольку проверка состояния сервера больше не требуется, `AFX_SQL_SYNC` просто присваивает значение свойству `nRetCode`. Например, вместо звонка  
  
 [!code-cpp[NVC_MFCDatabase&#40;](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 Вы можете просто задать назначения  
  
 [!code-cpp[NVC_MFCDatabase&#41;](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
  
##  <a name="afxgethenv"></a>AfxGetHENV  
 Возвращенный дескриптор можно использовать в прямые вызовы ODBC, но не должно закрыть дескриптор или Предположим, что дескриптор является по-прежнему правильными и доступными после любой существующий `CDatabase`- или `CRecordset`-производных объектов уничтожено.  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор среды ODBC в настоящий момент каким MFC. Может быть `SQL_HENV_NULL` при наличии не [CDatabase](../../mfc/reference/cdatabase-class.md) объекты и не [CRecordset](../../mfc/reference/crecordset-class.md) используемых объектов.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

