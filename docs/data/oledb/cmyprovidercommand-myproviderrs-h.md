---
title: CMyProviderCommand (MyProviderRS.H) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 919455c1f0e1bae0491226e2f2d0f53bb35f7ad8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046606"
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand (MyProviderRS.H)

`CMyProviderCommand` Класс является реализацией для объекта команды поставщика. Она предоставляет реализацию для `IAccessor`, `ICommandText`, и `ICommandProperties` интерфейсов. `IAccessor` Интерфейс является таким же, как в наборе строк. Объект команды использует метод доступа для указания привязки параметров. Объект набора строк использует их для указания привязки выходных столбцов. `ICommandText` Интерфейс является эффективным методом для текстового указания команды. В этом примере используется `ICommandText` интерфейс позже, при добавлении пользовательского кода; оно также переопределяет `ICommand::Execute` метод. `ICommandProperties` Интерфейс обрабатывает все свойства для объектов команд и наборов строк.  
  
```cpp  
// CMyProviderCommand  
class ATL_NO_VTABLE CMyProviderCommand :   
class ATL_NO_VTABLE CMyProviderCommand :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IAccessorImpl<CMyProviderCommand>,  
   public ICommandTextImpl<CMyProviderCommand>,  
   public ICommandPropertiesImpl<CMyProviderCommand>,  
   public IObjectWithSiteImpl<CMyProviderCommand>,  
   public IConvertTypeImpl<CMyProviderCommand>,  
   public IColumnsInfoImpl<CMyProviderCommand>  
```  
  
`IAccessor` Интерфейс управляет все привязки, используемые в командах и наборах строк. Потребитель вызывает метод `IAccessor::CreateAccessor` с массивом `DBBINDING` структуры. Каждый `DBBINDING` структура содержит сведения о том, как привязок к столбцу следует (например, тип и длина). Поставщик получает структуры и определяет, как данные должны передаваться и нужны ли все преобразования. `IAccessor` Интерфейс используется в объекте команд для обработки параметров в команде.  
  
Объект команды также предоставляет реализацию `IColumnsInfo`. OLE DB требуется `IColumnsInfo` интерфейс. Этот интерфейс позволяет потребителю получить сведения о параметрах команды. Объект набора строк использует `IColumnsInfo` интерфейса для возврата сведений о выходных столбцов к поставщику.  
  
Поставщик также содержится интерфейс `IObjectWithSite`. `IObjectWithSite` Интерфейс реализован в ATL 2.0 и позволяет передать сведения о себе в дочерний элемент. Объект команды использует `IObjectWithSite` сведения, чтобы сообщать всем созданным объектам набора строк о кто их создал.  
  
## <a name="see-also"></a>См. также  

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)