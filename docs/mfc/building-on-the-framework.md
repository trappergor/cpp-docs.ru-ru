---
title: Сборка в платформе | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application-specific classes [MFC]
- application framework [MFC], building applications
- applications [MFC]
- MFC, application development
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca0ebd9bf03df8725c14df8d2aca1f7858b7b65
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396185"
---
# <a name="building-on-the-framework"></a>Сборка в платформе

Роль пользователя в Настройка приложения с помощью платформы MFC — для предоставления конкретного приложения исходный код и соединения компонентов, определив, какие сообщения и команды, к которым они могут реагировать неправильно. Используйте стандартные методики C++ и язык C++ производными предоставляется библиотекой классов свои собственные классы конкретного приложения, а также переопределить и расширить поведение базового класса.

Щелкните ссылку в следующих таблицах описаны общие последовательности операций, которые обычно выполняются и ваши обязанности и обязанности платформы:

- [Последовательность для построения приложений с помощью платформы](../mfc/sequence-of-operations-for-building-mfc-applications.md)

- [Последовательность операций для создания приложений OLE](../mfc/sequence-of-operations-for-creating-ole-applications.md)

- [Последовательность операций при создании элементов управления ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)

- [Последовательность операций для создания приложений баз данных](../mfc/sequence-of-operations-for-creating-database-applications.md)

В большинстве случаев вы можете выполнить эти таблицы как последовательность шагов по созданию приложения MFC, несмотря на то, что некоторые шаги являются альтернативные варианты. Например большинство приложений использует один тип класса представления из нескольких доступных типов.

## <a name="see-also"></a>См. также

[Общие разделы по MFC](../mfc/general-mfc-topics.md)

