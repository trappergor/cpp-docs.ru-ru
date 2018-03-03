---
title: "Потоки и классы ODBC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d1d922dfc34fa3e5530eca77a6501ad3e331fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-classes-and-threads"></a>Потоки и классы ODBC
Начиная с MFC версии 4.2, имеется поддержка многопоточности для классов MFC ODBC. Обратите внимание, что MFC не поддерживает многопоточность для классов DAO.  
  
 Поддержка многопоточности для классов ODBC имеет некоторые ограничения. Эти классы используют оболочку ODBC API, они ограничены многопоточности компонентов, на которых они построены. Например многие драйверы ODBC не являются потокобезопасными; Таким образом классы MFC ODBC не являются потокобезопасными при использовании с одним из этих драйверов. Следует проверить ли ваш драйвер является потокобезопасным.  
  
 При создании многопоточного приложения, следует с особой осторожностью использовать несколько потоков для управления одним объектом. Например, используя те же `CRecordset` объекта в двух потоков может привести к проблемам при извлечении данных; операция выборки в одном потоке может перезаписать данные, полученные в другой поток. Чаще всего применяются классы MFC ODBC в отдельных потоках — поделиться с вами открытого `CDatabase` нескольких потоках для использования общего подключения ODBC, с отдельным `CRecordset` объекта в каждом потоке. Обратите внимание, что не следует передавать неоткрытый `CDatabase` объект `CRecordset` объект в другом потоке.  
  
> [!NOTE]
>  Если необходимо иметь несколько потоков для управления и тот же объект, необходимо реализовать соответствующие методы синхронизации, такие как критические секции. Имейте в виду, что некоторые операции, такие как **откройте**, не защищены. Следует убедиться, что эти операции не вызываются одновременно из разных потоков.  
  
 Дополнительные сведения о создании многопоточных приложений см. в разделе [многопоточность](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Доступ к данным программирования (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)