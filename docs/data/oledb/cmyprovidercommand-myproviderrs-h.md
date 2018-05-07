---
title: CMyProviderCommand (MyProviderRS.H) | Документы Microsoft
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
ms.openlocfilehash: 8c18742d9b3b1039033ad8d42939e0f5a4578fbb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand (MyProviderRS.H)
`CMyProviderCommand` Класс является реализацией для объекта команды поставщика. Он обеспечивает реализацию `IAccessor`, `ICommandText`, и **ICommandProperties** интерфейсов. `IAccessor` Интерфейс является таким же, как в наборе строк. Объект команды использует метод доступа для указания привязки параметров. Объект набора строк использует их для указания привязки выходных столбцов. `ICommandText` Интерфейс является удобным способом для текстового указания команды. В этом примере используется `ICommandText` интерфейс позже, при добавлении пользовательского кода; оно также переопределяет `ICommand::Execute` метод. **ICommandProperties** интерфейс обрабатывает все свойства для объектов команд и наборов строк.  
  
```  
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
  
 `IAccessor` Интерфейс управляет всеми привязками, используемыми в командах и наборах строк. Потребитель вызывает метод **IAccessor::CreateAccessor** с массивом **DBBINDING** структуры. Каждый **DBBINDING** структура содержит сведения об обработке привязки столбцов (например, тип и длина). Поставщик получает структуры и определяет способ передачи данных и нужны ли какие-либо преобразования. `IAccessor` Интерфейс используется в объекте команд для обработки параметров команды.  
  
 Объект команды также предоставляет реализацию `IColumnsInfo`. OLE DB требует `IColumnsInfo` интерфейса. Этот интерфейс позволяет потребителю запрашивать сведения о параметрах команды. Объект набора строк использует `IColumnsInfo` интерфейс для возврата сведений о выходных столбцах поставщику.  
  
 Поставщик также содержится интерфейс `IObjectWithSite`. `IObjectWithSite` Интерфейс реализован в библиотеке ATL 2.0 и позволяет разработчику класса передавать сведения о потомкам. Объект команды использует `IObjectWithSite` сведения, чтобы сообщать всем созданным объектам набора строк о кто их создал.  
  
## <a name="see-also"></a>См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)