---
title: "Сообщение макросы схемы (MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f890e0675be58c8e20e313bea54b4145e2ce0bf3
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-mfc"></a>Макросы схемы сообщений (MFC)
Для поддержки схемы сообщений, MFC предоставляет следующие макросы:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>Объявление схемы сообщений и определение границ макросы  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](http://msdn.microsoft.com/library/c225e7e0-a81b-495c-97f9-3e0aa1f65036)|Объявляет, что схема сообщений будет использоваться в классе сопоставление сообщений с функциями (необходимо использовать в объявлении класса).|  
|[BEGIN_MESSAGE_MAP](http://msdn.microsoft.com/library/d9201e18-04e0-4639-9810-f15768627fc2)|Начинается определение схемы сообщений (необходимо использовать реализацию класса).|  
|[END_MESSAGE_MAP](http://msdn.microsoft.com/library/40f611f1-a3b4-4097-b683-091bf7cfab8b)|Завершает определение схемы сообщений (необходимо использовать реализацию класса).|  
  
### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений  
  
|||  
|-|-|  
|[ON_COMMAND](http://msdn.microsoft.com/library/f24f8bda-2cf4-49d5-aa3d-6f2e6bb003f2)|Указывает, какая функция будет обрабатывать сообщения указанную команду.|  
|[ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)|Указывает, какая функция будет обрабатывать сообщения уведомление указанного элемента управления.|  
|[ON_MESSAGE](http://msdn.microsoft.com/library/e2faeb13-9f6e-4c0d-9f6d-b2e141a0db1e)|Указывает, какая функция будет обрабатывать определенное пользователем сообщение.|  
|[ON_OLECMD](http://msdn.microsoft.com/library/6c86327c-3d48-42ac-9dae-e0ccd3a81793)|Указывает, какая функция будет обрабатывать команду меню из DocObject или его контейнера.|  
|[ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d)|Указывает, какая функция будет обрабатывать зарегистрированных пользователем сообщение.|  
|[ON_REGISTERED_THREAD_MESSAGE](http://msdn.microsoft.com/library/3f598bc2-b2f0-410f-8ba0-7714502170f3)|Указывает, какая функция будет обрабатывать зарегистрированных определяемых пользователем сообщений, при наличии `CWinThread` класса.|  
|[ON_THREAD_MESSAGE](http://msdn.microsoft.com/library/f718f47a-d5b1-4514-914b-e3fe2d919003)|Указывает, какая функция будет обрабатывать определенное пользователем сообщение при наличии `CWinThread` класса.|  
|[ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)|Указывает, какая функция будет обрабатывать сообщения команды обновления указанного пользовательского интерфейса.|  
  
### <a name="message-map-range-macros"></a>Макросы схемы сообщений диапазона  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0)|Указывает, какую функцию обработки диапазона идентификаторов команд, указанных в первые два параметра в макрос.|  
|[ON_UPDATE_COMMAND_UI_RANGE](http://msdn.microsoft.com/library/b7105bf1-44ad-4b00-b947-31478f964729)|Указывает, какой обработчик обновление будет обрабатывать диапазона идентификаторов команд, указанных в первые два параметра в макрос.|  
|[ON_CONTROL_RANGE](http://msdn.microsoft.com/library/46f0e1bb-569b-4b8b-9b80-89701d1cd7fd)|Указывает, какие функции будут обрабатывать уведомления из диапазона идентификаторов, указанных в качестве второго и третьего параметров для макроса элемента управления. Первый параметр является сообщение уведомления элемента управления, таких как **BN_CLICKED**.|  
  
 Дополнительные сведения о схемы сообщений, объявление схемы сообщений и определение границ макросы и макросы сопоставления сообщений см. [схемы сообщений](../../mfc/reference/message-maps-mfc.md) и [обработка сообщений и разделы сопоставления](../../mfc/message-handling-and-mapping.md). Дополнительные сведения о диапазонах схемы сообщений в разделе [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  
  
## <a name="see-also"></a>См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)



