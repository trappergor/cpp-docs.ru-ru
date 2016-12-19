---
title: "Поддержка COM+ 1.0 в проектах ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.MTS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, поддержка COM+ 1.0"
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Поддержка COM+ 1.0 в проектах ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[Мастер проектов ATL](../../atl/reference/creating-an-atl-project.md) может использоваться для создания проектов с базовой поддержкой компонентов COM\+ 1.0.  
  
 Модель COM\+ 1.0 предназначена для разработки распределенных приложений, основанных на компонентах.  Она также предоставляет инфраструктуру времени выполнения для развертывания и управления этими приложениями.  
  
 При установке флажка **Поддержка COM\+ 1.0** мастер изменяет скрипт построения на этапе связывания.  В частности, проект COM\+ 1.0 связывается со следующими библиотеками:  
  
-   comsvcs.lib  
  
-   Mtxguid.lib  
  
 При установке флажка **Поддержка COM\+ 1.0** можно также выбрать параметр **Поддержка регистратора компонентов**.  Регистратор компонентов позволяет объекту COM\+ 1.0 получать список компонентов, регистрировать компоненты или отменять регистрацию компонентов \(по\-отдельности или сразу для всех\).  
  
## См. также  
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Конфигурации по умолчанию проекта ATL](../../atl/reference/default-atl-project-configurations.md)