---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
- ccustomcommand
- customrs.h
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: b10d7bccae6fa9b86d072b8e13791f23516b2c63
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028565"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand` Класс является реализацией для объекта команды поставщика. Она предоставляет реализацию для `IAccessor`, `ICommandText`, и `ICommandProperties` интерфейсов. `IAccessor` Интерфейс является таким же, как в наборе строк. Объект команды использует метод доступа для указания привязки параметров. Объект набора строк использует их для указания привязки выходных столбцов. `ICommandText` Интерфейс является эффективным методом для текстового указания команды. В этом примере используется `ICommandText` интерфейс позже, при добавлении пользовательского кода; оно также переопределяет `ICommand::Execute` метод. `ICommandProperties` Интерфейс обрабатывает все свойства для объектов команд и наборов строк.

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor` Интерфейс управляет все привязки, используемые в командах и наборах строк. Потребитель вызывает метод `IAccessor::CreateAccessor` с массивом `DBBINDING` структуры. Каждый `DBBINDING` структура содержит сведения о том, как привязок к столбцу следует (например, тип и длина). Поставщик получает структуры и определяет, как данные должны передаваться и нужны ли все преобразования. `IAccessor` Интерфейс используется в объекте команд для обработки параметров в команде.

Объект команды также предоставляет реализацию `IColumnsInfo`. OLE DB требуется `IColumnsInfo` интерфейс. Этот интерфейс позволяет потребителю получить сведения о параметрах команды. Объект набора строк использует `IColumnsInfo` интерфейса для возврата сведений о выходных столбцов к поставщику.

Поставщик также содержится интерфейс `IObjectWithSite`. `IObjectWithSite` Интерфейс реализован в ATL 2.0 и позволяет передать сведения о себе в дочерний элемент. Объект команды использует `IObjectWithSite` сведения, чтобы сообщать всем созданным объектам набора строк о кто их создал.

## <a name="see-also"></a>См. также

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)