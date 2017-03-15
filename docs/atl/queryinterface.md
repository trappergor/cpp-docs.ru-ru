---
title: "QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "интерфейсы, доступность"
  - "интерфейсы, указатели"
  - "QueryInterface - метод"
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Хотя механизмы объект может представить функциональные возможности его предоставляют статически \(\), прежде чем он создан базовый механизм модели COM использовать метод с именем **IUnknown** [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Каждый интерфейс является производным от **IUnknown**, поэтому каждый интерфейс имеет реализацию `QueryInterface`.  Независимо от реализации этот метод извлекает объект, используя идентификатор IID интерфейса, к которым вызывающий объект должен указатель.  , Если обозреватель, взаимодействующие, `QueryInterface` объекта получают указатель на интерфейс, а также при вызове `AddRef`.  В противном случае функция возвращает код ошибки **E\_NOINTERFACE**.  
  
 Обратите внимание, что необходимо повиноваться правилам [Подсчет ссылок](../atl/reference-counting.md) все время.  При вызове **Выпуск** указателя интерфейса для уменьшения счетчика ссылок, равное нулю, не следует использовать этот указатель снова.  Иногда можно получить слабую ссылку на объект \(то есть можно пожелать получить указатель на один из его интерфейсов без выполнить приращение счетчика ссылок\), но не желательно сделать путем вызова `QueryInterface` выполните **Выпуск**.  Указатель, полученный таким способом является недопустимым и не должен использоваться.  Этот более легко будет ясным при [\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md) указано, поэтому указание этот макрос полезный способ найти ссылку учета ошибок.  
  
## См. также  
 [Введение в COM](../atl/introduction-to-com.md)   
 [QueryInterface: Navigating in an Object](http://msdn.microsoft.com/library/windows/desktop/ms687230)