---
title: "Рекомендации по выбору между ATL и MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d912c6cd997c23b9623d20a104327fb6e4701494
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>Рекомендации по выбору между ATL и MFC
При разработке компонентов и приложений, можно выбрать между двумя подходами, ATL и MFC (библиотеки классов Microsoft Foundation).  
  
## <a name="using-atl"></a>С использованием ATL  
 ATL — быстрый, простой способ поддерживать небольшого размера и создание COM-компонента на языке C++. Используйте ATL для создания элемента управления, если все встроенные функции, предоставляемой библиотекой MFC автоматически не требуется.  
  
## <a name="using-mfc"></a>Использование MFC  
 MFC позволяет создавать полные, элементы управления ActiveX и активные документы. Если вы уже создали элемент управления с MFC, можно продолжить разработку в MFC. При создании нового элемента управления, рассмотрите возможность использования ATL, если все встроенные функции MFC не требуется.  
  
## <a name="using-atl-in-an-mfc-project"></a>Использование ATL в проект MFC  
 Можно добавить поддержку с использованием ATL в существующий проект MFC с помощью мастера. Дополнительные сведения см. в разделе [Добавление поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
## <a name="see-also"></a>См. также  
 [Введение в ATL](../atl/introduction-to-atl.md)

