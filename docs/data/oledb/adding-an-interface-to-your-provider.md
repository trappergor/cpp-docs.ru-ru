---
title: Добавление интерфейса в поставщик | Документы Microsoft
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
ms.openlocfilehash: 3d6bc5d1b6c47d2ffa26bffa98d47b930d6ed193
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093550"
---
# <a name="adding-an-interface-to-your-provider"></a>Добавление интерфейса в поставщик
Определения объекта, который требуется добавить интерфейс (обычно данных источника, набора строк, команды или сеанса объекты, созданные мастером поставщика OLE DB). Это возможно, необходимо добавить интерфейс для объекта, не поддерживается поставщиком. В этом случае запустите мастер ATL OLE DB Provider для создания объекта. Щелкните правой кнопкой мыши проект в представлении классов щелкните **добавить класс** из **добавить** меню, а затем нажмите **поставщика ATL OLE DB**. Вы можете разместить код интерфейса в отдельном каталоге, а затем скопируйте файлы в проект поставщика.  
  
 Если вы создали новый класс для поддержки интерфейса, следует наследовать от этого класса объект. Например, можно добавить класс **IRowsetIndexImpl** для объекта набора строк:  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
 Добавить интерфейс **COM_MAP** в объекте с помощью макроса COM_INTERFACE_ENTRY. Если файл сопоставления отсутствует, создайте его. Например:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Объект набора строк цепочки сопоставление родительского объекта, чтобы объект можно делегировать родительского класса. В этом примере добавьте макрос COM_INTERFACE_ENTRY_CHAIN карты:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)