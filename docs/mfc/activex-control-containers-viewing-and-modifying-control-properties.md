---
title: 'Контейнеры элементов управления ActiveX: Просмотр и изменение свойств элемента управления | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef443442cb19b9aaca82b74a0a5d8c72098d5cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340298"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>Контейнеры элементов управления ActiveX. Просмотр и изменение свойств элементов управления
При вставке элемента управления ActiveX в проекте полезно для просмотра и изменения свойств, поддерживаемых элементом управления ActiveX. В этой статье описывается использование редактора ресурсов Visual C++ для этого.  
  
 Если приложение контейнера элемента управления ActiveX использует внедренные элементы управления, можно просматривать и изменять свойства элемента управления в редакторе ресурсов. Можно также использовать редактор ресурсов для задания значений свойств во время разработки. Редактор ресурсов затем автоматически сохраняет эти значения в файл ресурсов проекта. Любой экземпляр элемента управления будет иметь его свойства инициализации значений этих параметров.  
  
 Эта процедура предполагает, что вы установили элемента управления в проект. Сведения см. в разделе [контейнеры элементов управления ActiveX: Вставка элемента управления в приложение контейнера элемента управления](../mfc/inserting-a-control-into-a-control-container-application.md).  
  
 Первым шагом при просмотре свойств элемента управления является добавление экземпляра элемента управления в проект шаблона диалогового окна.  
  
### <a name="to-view-the-properties-of-a-control"></a>Для просмотра свойств элемента управления  
  
1.  В представлении ресурсов откройте **диалоговое окно** папки.  
  
2.  Откройте ваш шаблон главного диалогового окна.  
  
3.  Вставка элемента управления ActiveX с помощью **Вставка элемента ActiveX** диалоговое окно. Дополнительные сведения см. в разделе [для просмотра и добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
4.  Выберите элемент управления ActiveX в диалоговом окне.  
  
5.  В окне «Свойства» выберите **свойства** кнопки.  
  
 Используйте **свойства** диалогового окна для изменения и тестировать новые свойства немедленно.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

