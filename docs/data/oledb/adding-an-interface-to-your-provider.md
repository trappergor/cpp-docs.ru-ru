---
title: Добавление интерфейса в поставщик
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: 295a7955b78918d6281a28b616f201869f37b01e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488677"
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