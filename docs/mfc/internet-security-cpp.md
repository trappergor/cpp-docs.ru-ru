---
title: Безопасность в Интернете (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b61df9a17903f50ea922edf9c29eee926063254
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055415"
---
# <a name="internet-security-c"></a>Безопасность в Интернете (C++)

Безопасность кода является серьезной проблемой для разработчиков, так и для пользователей веб-приложений. Рисках: вредоносный код, код, который подделки и код из неизвестных узлов или авторы.

Существует два основных подхода к безопасности при разработке для Интернета. Первый называется «песочницы». При таком подходе приложение только для конкретного набора интерфейсов API и исключены из потенциально опасные например файлового ввода-вывода, где программы может уничтожить данные на компьютере пользователя. Второй реализуется с помощью цифровых подписей. Такой подход называется «shrinkwrap» для использования в Интернете. Код проверки и подписываются с использованием закрытого ключа/public основная технология. Перед выполнением кода, его цифровая подпись проверяется, чтобы убедиться, что код является из известного источника прошедшего проверку подлинности, и что код не был изменен с момента его подписания.

В первом случае вы доверяете, что приложение не будет выполнять любой ущерба и заслуживает доверия приложения. Во втором цифровые подписи используются для проверки подлинности. Цифровая подпись — это отраслевой стандарт, используемый для идентификации и содержат сведения об издателе кода. Технологии этой компании основана на стандартах, включая RSA и X.509. Браузеры обычно позволяют пользователям выбрать, следует ли для загрузки и запуска кодом неизвестного происхождения.

## <a name="see-also"></a>См. также

[Задачи программирования для интернет-решений MFC](../mfc/mfc-internet-programming-tasks.md)<br/>
[Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

