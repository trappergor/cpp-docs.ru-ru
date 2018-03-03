---
title: "По умолчанию события элемента управления | Документы Microsoft"
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
- Dialog editor, default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls, events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83c7b6e4d019b895973345805027d428d7af766d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="default-control-events"></a>События по умолчанию элемента управления
Следующие имена элементов управления имеют соответствующие им события:  
  
|Имя элемента управления|Событие по умолчанию|  
|------------------|-------------------|  
|Анимация|**ACN_START**|  
|Флажок|**BN_CLICKED**|  
|Поле со списком|**CBN_SELCHANGE**|  
|Другой|**TTN_GETDISPINFO**|  
|Выбор даты и времени|**DTN_DATETIMECHANGE**|  
|Поле ввода|**EN_CHANGE**|  
|Область группы|(Неприменимо)|  
|Сочетания клавиш|**NM_OUTOFMEMORY**|  
|IP-адрес|**IPN_FIELDCHANGED**|  
|Список|**LVN_ITEMCHANGE**|  
|Список|**LBN_SELCHANGE**|  
|Месячный календарь|**MCN_SELCHANGE**|  
|Изображение элемента управления|(Неприменимо)|  
|Ход выполнения|**NM_CUSTOMDRAW**|  
|Кнопка|**BN_CLICKED**|  
|Переключатель|**BN_CLICKED**|  
|"Rich edit"|**EN_CHANGE**|  
|Полоса прокрутки|**NM_THEMECHANGED**|  
|Slider|**NM_CUSTOMDRAW**|  
|"Счетчик"|**UDN_DELTAPOS**|  
|Статический текст|(Неприменимо)|  
|Вкладка|**TCN_SELCHANGE**|  
|Дерево|**TVN_SELCHANGE**|  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Определение переменных-членов для элементов управления диалоговых окон](../windows/defining-member-variables-for-dialog-controls.md)   
 [Типы сообщений, связанных с объектами пользовательского интерфейса](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [Редактирование обработчика сообщений](../mfc/reference/editing-a-message-handler.md)   
 [Определение обработчика сообщений для отраженного сообщения](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [Объявление переменной на основании нового класса элемента управления](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [Переопределение виртуальной функции](../ide/overriding-a-virtual-function-visual-cpp.md)

