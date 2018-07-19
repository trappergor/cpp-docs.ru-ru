---
title: 'Исключения: Базы данных исключений | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83b3f4f54f467ca7f4fbd2a179fdbf01d54dfa89
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930242"
---
# <a name="exceptions-database-exceptions"></a>Исключения. Исключения баз данных
В этой статье описывается обработка исключений базы данных. Большая часть материала в данной статье применяется при работе с классами MFC для Open Database Connectivity (ODBC) или классы MFC для объектов доступа к данным (DAO). Будет явно отмечена как материалы, относящиеся к одной или другой модели. Ниже приведен список разделов.  
  
-   [Подходы к обработке исключений](#_core_approaches_to_exception_handling)  
  
-   [Пример обработки исключений для базы данных](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> Подходы к обработке исключений  
 Этот подход остается прежним и работе с DAO или ODBC.  
  
 Следует всегда писать обработчики исключений для обработки исключительных условиях.  
  
 Подход с использованием наиболее прагматичное использование для перехвата исключений базы данных является протестировать приложение с помощью сценариев исключение. Определите, скорее всего, исключения, которые могут возможны операции в коде, а также принудительно к возникновению исключения. Затем просмотрите выходные данные трассировки, чтобы увидеть, какие исключения или просматривать сведения об ошибке в отладчике. Это позволяет узнать, при котором возвращаются коды, отображаемые для исключения сценариев, которую вы используете.  
  
### <a name="error-codes-used-for-odbc-exceptions"></a>Коды ошибок, используемые для ODBC-исключения  
 Помимо кодов возврата, определенные платформой, которые имеют имена вида **AFX_SQL_ERROR_XXX**, некоторые [CDBExceptions](../mfc/reference/cdbexception-class.md) на основе [ODBC](../data/odbc/odbc-basics.md) коды возврата. Коды возврата для таких исключений имеют имена вида **SQL_ERROR_XXX**.  
  
 Коды возврата, определяемые платформой и определенные ODBC — что классы базы данных может возвращать приведен в подразделе [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) данными-членом класса `CDBException`. Дополнительные сведения о кодах возврата, определенном ODBC доступен в пакете SDK ODBC *Справочник программиста* в библиотеке MSDN.  
  
### <a name="error-codes-used-for-dao-exceptions"></a>Коды ошибок, используемые для исключения DAO  
 Для исключения DAO обычно доступна Дополнительные сведения. Сведения об ошибке доступны в трех данные-члены перехваченного [CDaoException](../mfc/reference/cdaoexception-class.md) объекта:  
  
-   [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) содержит указатель на [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) объект, инкапсулирующий сведения об ошибке в коллекцию в DAO объекты ошибок, связанных с базой данных.  
  
-   [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) содержит расширенный код ошибки из классов MFC DAO. Эти коды ошибок, которые имеют имена вида **AFX_DAO_ERROR_XXX**, приведен в подразделе член данных в `CDaoException`.  
  
-   [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) содержит OLE **SCODE** из DAO, если это применимо. Редко необходимо для работы с данным кодом ошибки, однако. Обычно Дополнительные сведения можно найти в других членах данных. В разделе элемент данных для получения дополнительных сведений **SCODE** значения.  
  
 Дополнительные сведения об ошибках, тип объекта ошибки DAO и Коллекция ошибок DAO DAO доступна внутри класса [CDaoException](../mfc/reference/cdaoexception-class.md).  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> Пример обработки исключений для базы данных  
 Следующий пример осуществляет попытку создать [CRecordset](../mfc/reference/crecordset-class.md)-производного объекта в куче с **новый** оператор, а затем откройте набор записей (для источника данных ODBC). Аналогичный пример для классов DAO см. «DAO исключение пример».  
  
### <a name="odbc-exception-example"></a>Пример исключений ODBC  
 [Откройте](../mfc/reference/crecordset-class.md#open) функция-член может возникнуть исключение (типа [CDBException](../mfc/reference/cdbexception-class.md) для классов ODBC), поэтому эта кода скобки `Open` вызов с **повторите** блока. Последующие **перехватывать** блок будет перехватывать `CDBException`. Можно проверить исключение сам объект, вызывается `e`, но в этом случае достаточно знать Сбой попытки создать набор записей. **Перехватывать** блок выдает сообщение об ошибке и выполняет очистку при удалении объекта набора записей.  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]  
  
### <a name="dao-exception-example"></a>Пример исключений DAO  
 Пример DAO похож на пример для ODBC, но можно получить дополнительные виды информации. Приведенный ниже код также пытается открыть набор записей. Если эта попытка вызывает исключение, вы проверяете членом данных в объект исключения сведения об ошибке. Как в предыдущем примере ODBC, возможно, будет достаточно, чтобы знать, что попытка создать набор записей завершилась неудачно.  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]  
  
 Этот код получает строку сообщения об ошибке из [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) член объекта исключения. MFC вводит этот элемент, когда он создает исключение.  
  
 Описание сведений об ошибках, возвращенных `CDaoException` см. в разделе классы [CDaoException](../mfc/reference/cdaoexception-class.md) и [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).  
  
 При работе с базами данных Microsoft Jet (.mdb) и в большинстве случаев при работе с ODBC, будут существовать только один объект ошибки. В редких случаях при использовании источника данных ODBC и несколько ошибок, можно использовать цикл через DAO в коллекцию ошибок, на основе количества ошибок, возвращаемых [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). При каждом прохождении цикла, вызовите [CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) для повторного заполнения `m_pErrorInfo` члена данных.  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

