---
title: ': Tn047 уменьшение требований к транзакциям базы данных | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96f3116f503ffa0ffc461ea2c1a0bdaf8947a0be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427021"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047. Уменьшение требований к транзакциям баз данных

Это техническое примечание, которые рассматриваются требования к транзакции классы базы данных MFC ODBC, теперь является устаревшим. До MFC 4.2, классы баз данных требуется, что курсоры сохранен на наборы записей после **CommitTrans** или **отката** операции. Если драйвер ODBC и СУБД, не поддерживают этот уровень хранения курсора, классы баз данных не включали транзакции.

Начиная с версии 4.2 MFC, устанавливается ограничение требует сохранения курсора классы баз данных. Транзакции будет включена, если драйвер поддерживает их. Однако теперь необходимо проверить эффект **CommitTrans** или **отката** операции на открытые наборы записей. См. в разделе функции-члены [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) и [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) Дополнительные сведения.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)

