---
title: Создание объекта-получателя без помощи мастера | Документация Майкрософт
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cd8412ed280c0a256ea8acb7274da5d6238134fc
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807801"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Создание объекта-получателя без помощи мастера

В следующем примере предполагается, что при добавлении поддержки объекта-получателя OLE DB в существующий проект ATL. Если вы хотите добавить поддержку потребителя OLE DB в приложение MFC, следует запустить мастер приложений MFC, создает необходимые поддержки, и вызов процедур MFC, необходимых для выполнения приложения.  
  
Добавление поддержки объекта-получателя OLE DB без использования мастера потребителя ATL OLE DB:  
  
- В файле pch.h добавьте следующее содержимое в `#include` инструкции:  
  
    ```cpp  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
Программным образом объект-получатель обычно выполняет следующую последовательность операций.  
  
1. Создайте класс записей пользователя, который привязывает столбцы к локальным переменным. В этом примере `CMyTableNameAccessor` является класс записей пользователя (см. в разделе [записи пользователей](../../data/oledb/user-records.md)). Этот класс содержит сопоставление столбцов и сопоставление параметров. Объявить элемент данных в класс записей пользователя для каждого поля, которые указываются в сопоставлении столбцов; для каждого из этих элементов данных необходимо также объявите элемент данных состояния и длины элемента данных. Дополнительные сведения см. в разделе [статус поля элементов данных в методах доступа](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    > Если вы создаете собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.  
  
- Создайте экземпляр источника данных и сеанса. Выбрать тип доступа и строк и затем создать экземпляр набора строк с помощью [CCommand](../../data/oledb/ccommand-class.md) или [CTable](../../data/oledb/ctable-class.md):  
  
    ```cpp  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
- Вызовите `CoInitialize` для инициализации COM. Обычно это называется в основной код. Пример:  
  
    ```cpp  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
- Вызовите [CDataSource::Open](../../data/oledb/cdatasource-open.md) или один из его вариантов.  
  
- Откройте подключение к источнику данных, откройте сеанс и откройте и инициализацию набора строк (и если команду, она выполняется):  
  
    ```cpp  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
- При необходимости, свойства набора строк, с помощью `CDBPropSet::AddProperty` и передавать их в качестве параметра `rs.Open`. Пример того, как это можно сделать, см. в разделе `GetRowsetProperties` в [разделе методы](../../data/oledb/consumer-wizard-generated-methods.md).  
  
- Теперь можно использовать набор строк для получения и обработки данных.  
  
- Когда приложение готово, закройте подключение, сеанса и набора строк:  
  
    ```cpp  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Если вы используете команды, может потребоваться вызвать `ReleaseCommand` после `Close`. В примере кода в [CCommand::Close](../../data/oledb/ccommand-close.md) показан способ вызова `Close` и `ReleaseCommand`.  
  
- Вызовите `CoUnInitialize` для отмены инициализации COM. Обычно это называется в основной код.  
  
    ```cpp  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>См. также  

[Создание объекта-получателя OLE DB](../../data/oledb/creating-an-ole-db-consumer.md)