---
title: Создание немодальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7da6d82257d1407dfcf4d6d3c15cdadbb8c0fa30
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685668"
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон

Для немодального диалогового окна необходимо предоставить собственный открытый конструктор в классе диалогового окна. Чтобы создать немодальное диалоговое окно, вызовите открытый конструктор, а затем вызовите функцию-член [создания](../mfc/reference/cdialog-class.md#create) объекта диалогового окна, чтобы загрузить ресурс диалогового окна. Можно вызвать метод **CREATE** либо во время, либо после вызова конструктора. Если в ресурсе диалога есть свойство **WS_VISIBLE**, диалоговое окно отображается немедленно. В противном случае необходимо вызвать свою функцию члена [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) .

## <a name="see-also"></a>См. также

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
