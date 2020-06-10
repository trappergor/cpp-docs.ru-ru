---
title: Создание немодальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7a6125e84438b0ef2ad541c26bda33051d483c8d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619642"
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон

Для немодального диалогового окна необходимо предоставить собственный открытый конструктор в классе диалогового окна. Чтобы создать немодальное диалоговое окно, вызовите открытый конструктор, а затем вызовите функцию-член [создания](reference/cdialog-class.md#create) объекта диалогового окна, чтобы загрузить ресурс диалогового окна. Можно вызвать метод **CREATE** либо во время, либо после вызова конструктора. Если в ресурсе диалога имеется свойство **WS_VISIBLE**, диалоговое окно отображается немедленно. В противном случае необходимо вызвать свою функцию члена [ShowWindow](reference/cwnd-class.md#showwindow) .

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
