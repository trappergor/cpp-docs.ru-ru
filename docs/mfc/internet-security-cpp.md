---
title: Безопасность в Интернете (C++) | Документы Microsoft
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
ms.openlocfilehash: f4454eceae2cc5f2e6b46510fe95889c664a568a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348855"
---
# <a name="internet-security-c"></a>Безопасность в Интернете (C++)
Безопасность кода — очень важна для разработчиков и пользователей веб-приложений. Существуют угрозы: вредоносный код, код, который подделан и код из неизвестных узлов или авторы.  
  
 Существует два основных подхода к безопасности при разработке для Интернета. Первый называется «песочницы». При таком подходе приложение только для определенного набора API-интерфейсов и исключен из потенциально опасные например файлового ввода-вывода, где программа может уничтожить данные на компьютере пользователя. Второй реализуется с помощью цифровых подписей. Такой подход называется «shrinkwrap» для использования в Интернете. Код проверки и подписи технологии закрытый ключ и открытого ключа. Перед выполнением кода, его цифровая подпись проверяется, чтобы убедиться, что код является из известных источников прошедшего проверку подлинности и что код не был изменен с момента подписания.  
  
 В первом случае отношения доверия, приложение не будет вреда и заслуживает доверия приложения. Во втором цифровые подписи используются для проверки подлинности. Цифровая подпись — это стандартный отраслевой, используемый для идентификации и предоставляются сведения об издателе кода. Его технология основана на стандартах, включая X.509 и RSA. Браузеры обычно позволяют пользователям выбрать, следует ли для загрузки и запуска кодом неизвестного происхождения.  
  
  
## <a name="see-also"></a>См. также  
 [Задачи программирования для Интернет MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

