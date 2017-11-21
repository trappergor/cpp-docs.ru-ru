---
title: "Поддержка COM + 1.0 в проектах ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.MTS
dev_langs: C++
helpviewer_keywords: ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33b93084a99154aea671c877aae7d80e48485202
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="com-10-support-in-atl-projects"></a>Поддержка COM + 1.0 в проекты ATL
Можно использовать [мастер проектов ATL](../../atl/reference/creating-an-atl-project.md) для создания проекта с базовой поддержкой компонентов COM + 1.0.  
  
 COM + 1.0 предназначена для разработки распределенных приложений, основанных на компонентах. Он также обеспечивает инфраструктуру времени выполнения для развертывания и управления этими приложениями.  
  
 При выборе **поддержка COM + 1.0** флажок установлен, мастер изменяет скрипт построения на этапе связывания. В частности COM + 1.0 проект ссылки на следующие библиотеки:  
  
-   Comsvcs.lib  
  
-   Mtxguid.lib  
  
 При выборе **поддержка COM + 1.0** флажок, вы также можете выбрать **поддержку регистрации компонента**. Регистрации компонента позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменять регистрацию компонентов (по отдельности или все одновременно).  
  
## <a name="see-also"></a>См. также  
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

