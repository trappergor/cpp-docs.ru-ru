---
title: Добавление поддержки ATL в проект MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.adding.atl.mfc
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2d7794d5c3777a208fef6371009771fc5b43c97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347072"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC
Если вы уже создали приложение на основе MFC, затем можно добавить поддержку для Active Template Library (ATL) легко, запустив мастер проектов MFC добавления поддержки ATL.  
  
> [!NOTE]
>  ATL и MFC не поддерживаются обычно в экспресс-выпусков Visual Studio.  
  
> [!NOTE]
>  Эта поддержка действует только для простых объектов COM, добавленных в проект библиотеки DLL или исполняемого файла MFC. Можно добавить другие COM-объекты (включая элементы управления ActiveX) в проекты MFC, но объекты могут не работать должным образом.  
  
### <a name="to-add-atl-support-to-your-mfc-project"></a>Добавление поддержки ATL в проект MFC  
  
1.  В обозревателе решений щелкните правой кнопкой мыши проект, к которому нужно добавить поддержку ATL.  
  
2.  В контекстном меню выберите **добавить**, а затем нажмите кнопку **Добавление класса**.  
  
3.  Выберите **Добавление поддержки ATL в проект MFC** значок.  
  
    > [!NOTE]
    >  Этот значок расположен в папке ATL в **категории** области.  
  
4.  При появлении запроса нажмите кнопку **Да** Добавление поддержки ATL.  
  
 Дополнительные сведения о том, как добавление поддержки ATL изменяет код проекта MFC см. в разделе [сведения об ATL поддерживает Added мастером ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)  
  
## <a name="see-also"></a>См. также  
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
