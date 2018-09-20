---
title: Обмен данными | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 504d2ff9f011770f75db73a63fa77b821281269b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435562"
---
# <a name="exchanging-data"></a>Обмен данными

Как и в большинстве диалоговых окнах, обмен данными между окно свойств и приложения является одним из наиболее важных функций страницы свойств. В этой статье описывается, как для выполнения этой задачи.

Обмен данными с свойств сводится к фактически обмен данными с помощью отдельных свойств страниц свойств. Процедуры для обмена данными со страницы свойств аналогичен случаю для обмена данными с диалоговым окном, поскольку [CPropertyPage](../mfc/reference/cpropertypage-class.md) объект является всего лишь специальные [CDialog](../mfc/reference/cdialog-class.md) объекта. Процедура использует преимущества платформы диалоговое окно данных exchange (DDX) услуги, что обеспечивает обмен данными между элементами управления в диалоговом поле и член переменных объект диалогового окна.

Важным различием между обмен данными с помощью свойств и обычный диалоговое окно является, что окно свойств имеет несколько страниц, поэтому необходимо обмениваться данными с все страницы в окне свойств. Дополнительные сведения о DDX см. в разделе [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md).

В следующем примере демонстрируется обмен данными между представлением и две страницы свойств:

[!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>См. также

[Страницы свойств](../mfc/property-sheets-mfc.md)

