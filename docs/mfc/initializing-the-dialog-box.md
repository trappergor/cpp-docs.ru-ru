---
title: Инициализация диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 1f8f8f7e40b1c873c4428542c628d02e250f14b4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626341"
---
# <a name="initializing-the-dialog-box"></a>Инициализация диалогового окна

После создания диалогового окна и всех его элементов управления, но непосредственно перед тем, как на экране появится диалоговое окно (любого из типов), вызывается функция-член [онинитдиалог](reference/cdialog-class.md#oninitdialog) объекта диалогового окна. Для модального диалогового окна это происходит во время `DoModal` вызова. Для немодального диалогового окна `OnInitDialog` вызывается при `Create` вызове метода. Обычно переопределяется `OnInitDialog` для инициализации элементов управления диалогового окна, например для установки исходного текста поля ввода. В `OnInitDialog` переопределении необходимо вызвать функцию члена базового класса `CDialog` `OnInitDialog` .

Если вы хотите задать цвет фона диалогового окна (и всех остальных диалоговых окон приложения), см. раздел [Настройка цвета фона диалогового окна](setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
