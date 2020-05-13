---
title: Предупреждение BSCMAKE BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 57858827439ac8cc11e3718d7a484124ae8a6d74
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197448"
---
# <a name="bscmake-warning-bk4504"></a>Предупреждение BSCMAKE BK4504

файл содержит слишком много ссылок; пропуск дальнейших ссылок из этого источника

Файл. cpp содержит более 64 000 ссылок на символы. Когда BSCMAKE обнаружил 64 000 ссылок в файле, он игнорирует все дальнейшие ссылки.

Чтобы устранить проблему, Разделите файл на два или более файлов, каждый из которых содержит менее 64 000 ссылок на символы, либо используйте директиву препроцессора `#pragma component(browser)`, чтобы ограничить символы, создаваемые для определенных ссылок. Дополнительные сведения см. в разделе [Component](../../preprocessor/component.md).
