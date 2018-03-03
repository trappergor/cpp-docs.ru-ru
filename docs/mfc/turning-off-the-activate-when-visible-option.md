---
title: "Отключение \"Активация при отображении\" | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25521d75921b377730a7f9afac71f2a60c055216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="turning-off-the-activate-when-visible-option"></a>Отключение параметра "Активация при отображении"
Элемент управления имеет два основных состояния: активных и неактивных. В большинстве случаев эти состояния были выделяемая ли элемент управления имел окна. Активный элемент управления имел окно. Неактивный элемент управления не поддерживались. С появлением активации без окна это различие больше не является универсальной, но по-прежнему распространяется на многие элементы управления.  
  
 По сравнению с остальными инициализации, выполняемой при помощи элемента управления ActiveX, создание окна — очень ресурсоемкая операция. В идеальном случае элемент управления отложить создание окна до крайней необходимости.  
  
 Многие элементы управления не обязательно должны быть активными в течение они видимы в контейнере. Часто элемент управления может оставаться в неактивном состоянии, пока пользователь выполняет операции, требующей он станет активным (например, щелчок мыши или нажатие клавиши TAB). Чтобы вызвать элемент управления остается неактивной, пока контейнера требуется активировать ее, удалите **OLEMISC_ACTIVATEWHENVISIBLE** флаг из элемента управления прочие флаги:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 **OLEMISC_ACTIVATEWHENVISIBLE** флаг опущен автоматически при отключении **Активация при отображении** в диалоговом окне [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страница MFC ActiveX Мастер элементов управления при создании элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

