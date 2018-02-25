---
title: "Поддержка транзакций в OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 84849b2d9bfd899a0ffd8a5d8eafe12f91a4adce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="supporting-transactions-in-ole-db"></a>Поддержка транзакций в OLE DB
Объект [транзакции](../../data/transactions-mfc-data-access.md) — это способ группировки или пакета, последовательность обновлений к источнику данных, либо все завершиться успешно и фиксируются одновременно, или (если один из них происходит сбой) не завершаются, и выполняется откат всей транзакции. Этот процесс гарантирует целостность результат в источнике данных.  
  
 OLE DB поддерживает транзакции с помощью следующих трех способов:  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>Связь между сеансами и транзакции  
 Объект источника данных можно создать один или несколько объектов сеанса, каждый из которых может быть внутри или за пределами области транзакции, в определенный момент времени.  
  
 Если сеанс не входит в транзакцию, все операции, выполняемые в течение этого сеанса в хранилище данных немедленно фиксируется при каждом вызове метода. (Это иногда называется режим автоматической фиксации или неявным режимом.)  
  
 Когда сеанс входит в транзакцию, все операции, выполняемые в течение этого сеанса в хранилище данных является частью транзакции и фиксируется или отменяться как единый блок. (Это иногда называется режим ручной фиксации.)  
  
 Поддержка транзакций зависит от поставщика. Если вы используете поставщик поддерживает транзакции, объект сеанса, который поддерживает **ITransaction** и **ITransactionLocal** может входить в простые (т. е невложенные) транзакции. Класс шаблонов OLE DB [CSession](../../data/oledb/csession-class.md) поддерживает эти интерфейсы и рекомендуемый способ реализации поддержки транзакций в Visual C++.  
  
## <a name="starting-and-ending-the-transaction"></a>Запуск и остановка транзакции  
 Можно вызвать `StartTransaction`, **зафиксировать**, и **прервать** методы в объекте набора строк в объекте-получателе.  
  
 Вызов **ITransactionLocal::StartTransaction** начинает новую локальную транзакцию. При запуске транзакции, любые изменения, используемые в последующих операциях не применяются фактически в хранилище данных до фиксации транзакции.  
  
 Вызов **ITransaction::Commit** или **ITransaction::Abort** завершает транзакцию. **Зафиксировать** приводит все изменения в пределах области транзакции для применения в хранилище данных. **Прервать** причины, все изменения в пределах транзакции отменяются и хранилище данных остается в состоянии он имел до запуска транзакции.  
  
## <a name="nested-transactions"></a>Вложенные транзакции  
 Объект [вложенные транзакции](https://msdn.microsoft.com/en-us/library/ms716985.aspx) возникает при запуске новой локальной транзакции, если активная транзакция уже существует в сеансе. Новая транзакция запускается как вложенную транзакцию под текущей транзакцией. Если поставщик не поддерживает вложенные транзакции, при вызове `StartTransaction` при уже существует активная транзакция на сеанс возвращает **значение XACT_E_XTIONEXISTS**.  
  
## <a name="distributed-transactions"></a>Распределенные транзакции  
 Распределенная транзакция предназначена для обновления распределенных данных; то есть данные на нескольких компьютерах в сети. Если вы хотите выполнить поддержку транзакций в распределенной системе, следует использовать платформу .NET Framework, а не поддержку транзакций OLE DB.  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)