---
title: Размещение элементов управления ActiveX с использованием ATL AXHost | Документы Microsoft
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
ms.openlocfilehash: 5057a077e8e778fa3d943b736d51d19af8f60fc6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356257"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>Размещение элементов управления ActiveX, с помощью ATL AXHost
Пример в этом разделе показано, как создание AXHost и как разместить элемент управления ActiveX, с помощью различных функций ATL. Также показано, как получение доступа к событиям элементов управления и приемником (с помощью [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) из элемента управления, который размещен. Этот образец размещает элемент управления календаря, в главном окне или в дочернем окне.  
  
 Обратите внимание, определение `USE_METHOD` символов. Можно изменить значение этого символа, чтобы принимать значения от 1 до 8. Значение символа определяет, каким образом будет создан элемент управления:  
  
-   Для четных значений `USE_METHOD`, вызов для создания узла подклассы окна и преобразует его в качестве узлов элемента управления. Для значений с нечетным код создает дочернее окно, который выступает в качестве узла.  
  
-   Для значений `USE_METHOD` от 1 до 4, доступ к элементу управления и прием событий, выполняются в вызове, который также создается узел. Значения в диапазоне от 5 до 8 запроса узла для интерфейсов и подключить приемник.  
  
 Ниже приведена сводная информация о вариантах.  
  
|USE_METHOD|Ведущее приложение|Управление доступом и прием событий|Функция показано|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|Дочерние окна|Один шаг|CreateControlLicEx|  
|2|Главное окно|Один шаг|AtlAxCreateControlLicEx|  
|3|Дочерние окна|Один шаг|CreateControlEx|  
|4|Главное окно|Один шаг|AtlAxCreateControlEx|  
|5|Дочерние окна|Несколько шагов|CreateControlLic|  
|6|Главное окно|Несколько шагов|AtlAxCreateControlLic|  
|7|Дочерние окна|Несколько шагов|CreateControl|  
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

