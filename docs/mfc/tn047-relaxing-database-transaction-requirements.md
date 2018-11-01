---
title: TN047. Уменьшение требований к транзакциям баз данных
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: d609576c5ffda1a3ba8021e6a459943092c40e98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658839"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047. Уменьшение требований к транзакциям баз данных

Это техническое примечание, которые рассматриваются требования к транзакции классы базы данных MFC ODBC, теперь является устаревшим. До MFC 4.2, классы баз данных требуется, что курсоры сохранен на наборы записей после **CommitTrans** или **отката** операции. Если драйвер ODBC и СУБД, не поддерживают этот уровень хранения курсора, классы баз данных не включали транзакции.

Начиная с версии 4.2 MFC, устанавливается ограничение требует сохранения курсора классы баз данных. Транзакции будет включена, если драйвер поддерживает их. Однако теперь необходимо проверить эффект **CommitTrans** или **отката** операции на открытые наборы записей. См. в разделе функции-члены [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) и [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) Дополнительные сведения.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)

