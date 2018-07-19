---
title: Размещение элементов управления ActiveX, с помощью ATL AXHost | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e26fd9e80b96c2b0196e3fd0e11b9c97f0f3bff3
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027210"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>Размещение элементов управления ActiveX, с помощью ATL AXHost
Пример в этом разделе показано, как создать AXHost и как для размещения элемента управления ActiveX, с помощью различных функций ATL. Также показано, как для доступа к событиям элемента управления и в качестве приемника (с помощью [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) из элемента управления, который размещается. Этот образец размещает элемент управления Calendar в главном окне или в дочернем окне.  
  
 Обратите внимание, что определение символа USE_METHOD. Можно изменить значение этого символа, чтобы принимать значения от 1 до 8. Значение символа определяет, как будет создан элемент управления:  
  
-   Для значений с четными номерами USE_METHOD, вызов для создания узла подклассы окна и преобразует его в узел управления. Для нечетные значения код создает дочернее окно, который выступает в качестве узла.  
  
-   Для значения USE_METHOD от 1 до 4, доступ к элементу управления и прием событий, выполняются в вызове, создающий размещение. Значения в диапазоне от 5 до 8 запроса узла для интерфейсов и подключить приемника.  
  
Ниже приведена сводная информация о вариантах.  
  
|USE_METHOD|Ведущее приложение|Управление доступом и прием|Демонстрируются функции|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|Дочернее окно|Один шаг|CreateControlLicEx|  
|2|Главное окно|Один шаг|AtlAxCreateControlLicEx|  
|3|Дочернее окно|Один шаг|CreateControlEx|  
|4|Главное окно|Один шаг|AtlAxCreateControlEx|  
|5|Дочернее окно|Несколько шагов|CreateControlLic|  
|6|Главное окно|Несколько шагов|AtlAxCreateControlLic|  
|7|Дочернее окно|Несколько шагов|CreateControl|  
|8|Главное окно|Несколько шагов|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [Класс CAxWindow2T](../atl/reference/caxwindow2t-class.md)   
 [Интерфейс IAxWinHostWindowLic](../atl/reference/iaxwinhostwindowlic-interface.md)

