---
title: "Обмен данными | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 172b03278ceede44f06b846c8b4f066e9f141e3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exchanging-data"></a>Обмен данными
Как и в большинстве диалоговых окон, обмен данными между окно свойств и приложением является одним из наиболее важных функций страницы свойств. В этой статье описывается выполнения этой задачи.  
  
 Обмен данными с вкладкой свойств сводится фактически обмена данными с помощью отдельных свойств страниц свойств. Процедура для обмена данными с помощью страницы свойств не так же, как обмен данными с диалоговым окном, поскольку [CPropertyPage](../mfc/reference/cpropertypage-class.md) объект является просто специальный [CDialog](../mfc/reference/cdialog-class.md) объекта. Процедура использует преимущества услуги данных exchange (DDX) framework диалогового окна, что обеспечивает обмен данными между элементами управления в диалоговом окне поле и член переменных объект диалогового окна.  
  
 Важное отличие между обмен данными с вкладкой свойств и с обычным диалоговым окном, имеет окно свойств нескольких страниц, поэтому должен обмениваться данными с всех страниц в окне свойств. Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md).  
  
 В следующем примере показан обмен данными между представлением и две страницы вкладки свойств:  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../mfc/property-sheets-mfc.md)

