---
title: 'TN047: Уменьшение баз требований к транзакциям баз данных | Документы Microsoft'
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
ms.openlocfilehash: be5870efacb61d5c0bb74f85427c41f787d2edd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380938"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047. Уменьшение требований к транзакциям баз данных
Этот технический Обратите внимание, что обсуждалось требований к транзакциям классов базы данных MFC ODBC, больше не используется. До MFC 4.2 классы баз данных требуется сохранение курсоров с наборами записей после **CommitTrans** или **отката** операции. Если драйвер ODBC и СУБД, не поддерживает этот уровень Сохранение курсора, классы базы данных не была включена транзакции.  
  
 Начиная с MFC версии 4.2, устанавливается ограничение требует сохранения курсора классы баз данных. Будут включены транзакции, если драйвер поддерживает их. Однако теперь необходимо проверить влияние **CommitTrans** или **отката** операции на открытые наборы записей. Функции-члены в разделе [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) и [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

