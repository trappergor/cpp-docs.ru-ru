---
title: "Создание объекта-получателя без помощи мастера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a61de0a4621f6f9387da23093f9f450749129ac3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Создание объекта-получателя без помощи мастера
В следующем примере предполагается, что добавляется поддержка потребителя OLE DB в существующий проект ATL. Если вы хотите добавить поддержку потребителя OLE DB в приложение MFC, следует запустить мастер приложений MFC, создает необходимые поддержки, и вызов процедур MFC, необходимых для выполнения приложения.  
  
 Добавление поддержки объекта-получателя OLE DB без использования мастера потребителя ATL OLE DB:  
  
-   В файле Stdafx.h, добавив следующие `#include` инструкции:  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 Программным образом объект-получатель обычно выполняет следующую последовательность операций.  
  
-   Создайте класс записей пользователя, который привязывает столбцы к локальным переменным. В этом примере `CMyTableNameAccessor` является класс записей пользователя (в разделе [записей пользователей](../../data/oledb/user-records.md)). Этот класс содержит сопоставление столбцов и сопоставление параметров. Объявите член данных в классе записи пользователя для каждого поля, заданные в сопоставлении столбцов; для каждого из этих элементов данных также объявите элемент данных состояния и элемент данных длины. Дополнительные сведения см. в разделе [членов данных состояния поля в создаваемых мастером методах доступа](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  При написании собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.  
  
-   Создайте экземпляр источника данных и сеанса. Выбрать тип доступа и строк для использования, а затем экземпляр набора строк с помощью [CCommand](../../data/oledb/ccommand-class.md) или [CTable](../../data/oledb/ctable-class.md):  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
-   Вызовите **CoInitialize** для инициализации COM. Обычно вызывается в основном коде. Пример:  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Вызовите [CDataSource::Open](../../data/oledb/cdatasource-open.md) или один из его вариантов.  
  
-   Открытие подключения к источнику данных, открывает сеанс, откройте и инициализацию набора строк (и если это команда, она выполняется):  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   При необходимости, свойства набора строк, с помощью `CDBPropSet::AddProperty` и передавать их в качестве параметра `rs.Open`. Примером этого является см [методы, создаваемые мастером потребителя](../../data/oledb/consumer-wizard-generated-methods.md).  
  
-   Теперь можно использовать набор строк для получения и обработки данных.  
  
-   Когда приложение заканчивает работу, закройте соединение, сеансов и набора строк:  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     При использовании команды может потребоваться вызвать `ReleaseCommand` после **закрыть**. В примере кода в [CCommand::Close](../../data/oledb/ccommand-close.md) показано, как вызвать **закрыть** и `ReleaseCommand`.  
  
-   Вызовите **CoUnInitialize** отменить инициализацию COM. Обычно вызывается в основном коде.  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>См. также  
 [Создание объекта-получателя OLE DB](../../data/oledb/creating-an-ole-db-consumer.md)