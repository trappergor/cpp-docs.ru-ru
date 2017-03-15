---
title: "CMyProviderCommand (MyProviderRS.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyprovidercommand"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderCommand - класс (MyProviderRS.H)"
  - "поставщики OLE DB, файлы, созданные мастером"
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderCommand (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMyProviderCommand` обеспечивает реализацию объекта команд поставщика.  Он предоставляет реализацию интерфейсов `IAccessor`, `ICommandText` и **ICommandProperties**.  Интерфейс `IAccessor` не отличается от интерфейса для набора строк.  Объект команд использует метод доступа для указания привязки параметров.  Объект набора строк использует их для указания привязки выходных столбцов.  Интерфейс `ICommandText` полезен для текстового указания команды.  В этом примере интерфейс `ICommandText` используется позже, при добавлении пользовательского кода; в примере также переопределяется метод `ICommand::Execute`.  Интерфейс **ICommandProperties** обрабатывает все свойства объекта команд и объекта набора строк.  
  
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
  
 Интерфейс `IAccessor` управляет всеми привязками, используемыми в командах и наборах строк.  Объект\-получатель вызывает метод **IAccessor::CreateAccessor** с массивом структур **DBBINDING**.  В каждой структуре **DBBINDING** содержатся сведения о том, как следует проводить привязку столбцов \(например, тип данных и длина столбца\).  Поставщик получает структуры и определяет, как следует передавать данные и нужны ли какие\-либо преобразования.  Интерфейс `IAccessor` используется в объекте команд для обработки параметров команды.  
  
 В объекте команд также предоставляется реализация `IColumnsInfo`.  Для OLE DB требуется интерфейс `IColumnsInfo`.  Он позволяет объекту\-получателю запрашивать сведения о параметрах команды.  Объект набора строк использует интерфейс `IColumnsInfo`, чтобы передавать сведения о выходных столбцах поставщику.  
  
 В поставщике также содержится интерфейс `IObjectWithSite`.  Интерфейс `IObjectWithSite` реализован в библиотеке ATL 2.0, он позволяет разработчику класса передавать сведения о классе потомкам.  Объект команд использует сведения интерфейса `IObjectWithSite`, чтобы сообщать всем созданным объектам набора строк сведения об их создателе.  
  
## См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)