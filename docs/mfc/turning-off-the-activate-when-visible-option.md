---
title: Отключение параметра "Активация при видимым" | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cb585496e6acf1c0ad94a43500e6d9a4830a2ac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381287"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Отключение параметра "Активация при отображении"

Элемент управления имеет два основных состояний: активных и неактивных. В большинстве случаев эти состояния были различаются по ли элемент управления содержит окно. Активный элемент управления был окно. элемент управления неактивным, этого не сделали. С появлением активации без окна это различие, больше не является универсальным, но при этом по-прежнему применяется к многим элементам управления.

По сравнению с остальным членам инициализации, выполняемой при помощи элемента управления ActiveX, создание окна является очень ресурсоемкая операция. В идеальном случае элемент управления отложить создание окна до крайней необходимости.

Многие элементы управления не обязательно должны быть активными в течение они видны в контейнере. Часто элемент управления может оставаться в неактивном состоянии, пока пользователь не выполнит это операция, требующая он станет активным (например, щелкнув мышью или нажатие клавиши TAB). Чтобы вызвать элемент управления для остается неактивной, пока контейнер должен активировать ее, удалите **OLEMISC_ACTIVATEWHENVISIBLE** флаг из элемента управления прочие флаги:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

**OLEMISC_ACTIVATEWHENVISIBLE** флаг опущен автоматически в том случае, если вы отключите **Активация при отображении** в диалоговом окне [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) странице MFC ActiveX Мастер элементов управления при создании элемента управления.

## <a name="see-also"></a>См. также

[Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

