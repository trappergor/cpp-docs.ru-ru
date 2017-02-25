---
title: "Marshaling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "интерфейсы COM, маршалинг"
  - "маршалинг"
  - "маршалинг, COM-взаимодействие"
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Marshaling
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Метод модели COM маршалинга обеспечивает интерфейсы, предоставляемые объектом в одном процессе, который необходимо использовать в другом процессе.  В маршалинге модель COM \(код или код польз представленный реализацией интерфейса\) оба для упаковки параметров метода в формате, который могут перемещаться между процессами \(так же, как с помощью сети к процессу, выполняющемуся на других компьютерах\) и распаковать эти параметры с другой стороны.  Кроме того, модель COM должен выполнить те же шаги при возврате из вызова.  
  
> [!NOTE]
>  Маршалинг обычно не требуется, когда интерфейс предоставленный объект используется в том же процессе, что и объект.  Однако маршалировать может быть необходим между потоками.  
  
## См. также  
 [Введение в COM](../atl/introduction-to-com.md)   
 [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)