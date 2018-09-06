---
title: Классы окон ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing
- superclassing, ATL
ms.assetid: 1d12b708-de3e-49d5-9e41-42fe4769fa62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e67849da9eebf9f150c4363e05a6f3fdcb943c0d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756393"
---
# <a name="atl-window-classes"></a>Классы окон ATL

ATL содержит несколько классов, которые позволяют использовать и реализовать windows. Эти классы, как другие классы ATL обеспечивают эффективную реализацию, не создать нагрузку на ваш код.

В этом разделе описываются классы окон ATL и объясняется, как их использовать.

## <a name="in-this-section"></a>В этом разделе

[Введение в классы окон ATL](../atl/introduction-to-atl-window-classes.md)  
Краткое описание каждого класса окна ATL и ссылки на справочные материалы по их.

[Использование окна](../atl/using-a-window.md)  
Описывается использование `CWindow` управления окном.

[Реализация окна](../atl/implementing-a-window.md)  
Обработчики сообщений, схемы сообщений и с помощью `CWindowImpl`. Содержит сведения о Создание надклассов и подклассов.

[Реализация диалогового окна](../atl/implementing-a-dialog-box.md)  
Описаны два метода для добавления класса диалогового окна и показан пример кода.

[Использование размещенных окон](../atl/using-contained-windows.md)  
Описание размещенных окон в ATL, которые являются windows, которые делегируют свои сообщения для объекта-контейнера вместо их обработки в своего класса.

[Основные сведения о характеристиках окна](../atl/understanding-window-traits.md)  
Описание классов признаки окно в ATL Эти классы предоставляют простой способ для стандартизации стилей, которые используются для создания объекта окна.

## <a name="related-sections"></a>Связанные разделы

[ATL](../atl/active-template-library-atl-concepts.md)  
Ссылки на разделы о программировании с использованием библиотеки ATL.

[Классы с поддержкой окон](../atl/windows-support-classes.md)  
Перечисляет дополнительные классы ATL, поддерживающих windows и схемы сообщений в ATL

