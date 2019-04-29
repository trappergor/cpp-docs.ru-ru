---
title: Предупреждение BSCMAKE BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 7ffcb7c2e6ae512006ccd29c87b05c53fdfcaef5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279308"
---
# <a name="bscmake-warning-bk4504"></a>Предупреждение BSCMAKE BK4504

файл содержит слишком много ссылок; Пропуск дальнейшие ссылки из этого источника

CPP-файл содержит более 64 000 ссылки на символы. При обнаружении 64 000 ссылки в файле BSCMAKE игнорирует все дальнейшие ссылки.

Устранить проблему, либо разбить файл на два или несколько файлов, каждый из которых имеет не более 64 000 ссылок на символы воспользоваться `#pragma component(browser)` директива препроцессора, ограничение символы, которые создаются для определенной ссылки. Дополнительные сведения см. в разделе [компонент](../../preprocessor/component.md).