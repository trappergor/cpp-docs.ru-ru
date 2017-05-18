---
title: "Поддержка COM + 1.0 в проектах ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.MTS
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7521c1dae6fd29b8b951d23fe33c91179d4b46ed
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="com-10-support-in-atl-projects"></a>Поддержка COM + 1.0 в проектах ATL
Можно использовать [ATL Project Wizard](../../atl/reference/creating-an-atl-project.md) для создания проекта с базовой поддержкой компонентов COM + 1.0.  
  
 COM + 1.0 предназначена для разработки распределенных приложений, основанных на компонентах. Он также предоставляет инфраструктуру времени выполнения для развертывания и управления этими приложениями.  
  
 При выборе **поддержка COM + 1.0** флажок, мастер изменяет скрипт построения на этапе связывания. В частности COM + 1.0 проекта ссылки на следующие библиотеки:  
  
-   Comsvcs.lib  
  
-   Mtxguid.lib  
  
 При выборе **поддержка COM + 1.0** флажок, можно также выбрать **Поддержка регистратора компонентов**. Регистратор компонентов позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменять регистрацию компонентов (по отдельности или все сразу).  
  
## <a name="see-also"></a>См. также  
 [Основы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Программирование с использованием ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Конфигурации проекта ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)


