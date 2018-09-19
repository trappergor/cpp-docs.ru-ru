---
title: Добавление интерфейса в поставщик | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f50459550c91f07c12f6f18b3fbbaa5622ab7408
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032397"
---
# <a name="adding-an-interface-to-your-provider"></a>Добавление интерфейса в поставщик

Определения объекта, который вы хотите добавить интерфейс (обычно данных источника, набор строк, команды или сеанса объекты созданные мастером поставщика OLE DB). Вполне возможно, что объект, необходимо добавить интерфейс — это приложения, не поддерживается поставщиком. В этом случае запустите мастер ATL OLE DB Provider для создания объекта. Щелкните правой кнопкой мыши проект в представлении классов щелкните **Добавление класса** из **добавить** меню, а затем щелкните **поставщика ATL OLE DB**. Может потребоваться разместить код интерфейса в отдельном каталоге, а затем скопируйте файлы в проект поставщика.  
  
Если вы создали новый класс для поддержки интерфейса, следует наследовать от этого класса объект. Например, можно добавить класс **IRowsetIndexImpl** для объекта набора строк:  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
Добавить интерфейс **COM_MAP** в объекте с помощью макроса COM_INTERFACE_ENTRY. Если файл сопоставления отсутствует, создайте его. Пример:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
Объект набора строк цепочка карты родительского объекта таким образом, объект можно делегировать в родительский класс. В этом примере добавьте макрос COM_INTERFACE_ENTRY_CHAIN карты:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>См. также  

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)