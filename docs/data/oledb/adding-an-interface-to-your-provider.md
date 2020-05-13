---
title: Добавление интерфейса в поставщик
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: b13d1224388dc7d3218dea1c70b5aa8a595fcbdb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212335"
---
# <a name="adding-an-interface-to-your-provider"></a>Добавление интерфейса в поставщик

> [!NOTE]
> Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

Определите, к какому объекту вы хотите добавить интерфейс (обычно это объекты источника данных, набора строк, команды или сеанса, созданные **мастером поставщика OLE DB**). Возможно, что объект, к которому вам нужно добавить интерфейс, является тем, который в настоящее время не поддерживается вашим провайдером. В таком случае запустите **мастер поставщика ATL OLE DB** для создания объекта. Щелкните правой кнопкой мыши проект в **представлении классов**, в меню щелкните **Добавить** > **Новый элемент**, выберите **Установленные** > **Visual C++**  > **ATL**, а затем щелкните **Поставщик OLEDB библиотеки ATL**. Может потребоваться разместить код интерфейса в отдельном каталоге, а затем скопировать файлы в проект поставщика.

Если вы создали новый класс для поддержки интерфейса, сделайте объект наследуемым от этого класса. Например, можно добавить класс `IRowsetIndexImpl` для объекта набора строк.

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

Добавьте интерфейс в COM_MAP объекта с помощью макроса COM_INTERFACE_ENTRY. Если файл сопоставления отсутствует, создайте его. Пример:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

Для объекта набора строк поставьте в цепочку карту своего родительского объекта, чтобы объект мог делегировать его родительскому классу. В этом примере добавьте макрос COM_INTERFACE_ENTRY_CHAIN в карты.

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
