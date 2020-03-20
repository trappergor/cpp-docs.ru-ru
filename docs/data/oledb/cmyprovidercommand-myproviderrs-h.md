---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- ccustomcommand
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: 61bd60b63490303c65729843c3c0351a570a8056
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545729"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

Класс `CCustomCommand` является реализацией для объекта команды поставщика. Он обеспечивает реализацию интерфейсов `IAccessor`, `ICommandText`и `ICommandProperties`. Интерфейс `IAccessor` тот же, что и в наборе строк. Объект Command использует метод доступа для указания привязок для параметров. Объект набора строк использует их для указания привязок для выходных столбцов. Интерфейс `ICommandText` — это удобный способ указания команды в текстовом виде. В этом примере интерфейс `ICommandText` используется позже при добавлении пользовательского кода. Он также переопределяет метод `ICommand::Execute`. Интерфейс `ICommandProperties` обрабатывает все свойства для объектов Command и Rowset.

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

Интерфейс `IAccessor` управляет всеми привязками, используемыми в командах и наборах строк. Потребитель вызывает `IAccessor::CreateAccessor` с массивом структур `DBBINDING`. Каждая структура `DBBINDING` содержит сведения о том, как должны обрабатываться привязки столбцов (например, тип и длина). Поставщик получает структуры, а затем определяет способ передачи данных и необходимость каких бы то ни было преобразований. Интерфейс `IAccessor` используется в объекте Command для управления любыми параметрами в команде.

Объект Command также предоставляет реализацию `IColumnsInfo`. Для OLE DB требуется интерфейс `IColumnsInfo`. Интерфейс позволяет потребителю получать сведения о параметрах из команды. Объект набора строк использует интерфейс `IColumnsInfo` для возвращения сведений о выходных столбцах поставщику.

Поставщик также содержит интерфейс с именем `IObjectWithSite`. Интерфейс `IObjectWithSite` был реализован в ATL 2,0 и позволяет разработчику передавать сведения о себе своему дочернему элементу. Объект Command использует сведения о `IObjectWithSite`, чтобы сообщить всем созданным объектам набора строк о том, кто их создал.

## <a name="see-also"></a>См. также:

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)