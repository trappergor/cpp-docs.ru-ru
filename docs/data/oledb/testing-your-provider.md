---
title: "Тестирование поставщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 551ccfdf236eb5828b1d41ae8867acdb259b1d4f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="testing-your-provider"></a>Тестирование поставщика
Перед выпуском поставщика, следует выполнить следующие тесты в указанном порядке. Эти тесты убедитесь, что функции поставщика должным образом для большинства потенциальных пользователей.  
  
1.  Тестирование с помощью поставщика [потребителя](../../data/oledb/creating-an-ole-db-consumer.md) приложения, написанные на шаблоны потребителя OLE DB. Тестовый объект-получатель должен охватывать все функциональные области поставщика (весь код, которые были добавлены или изменены).  
  
2.  Протестируйте поставщик, используя приложение-потребитель, написанного с использованием ADO. Большинство разработчиков (особенно разработчиков Microsoft Visual Basic и Microsoft C#) для приложения-потребители использовать ADO или ADO.NET. Тестовый объект-получатель должен охватывать все функциональные области поставщика. Пример приложения потребителя ADO см. в разделе [примеры кода ADO в Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx).  
  
3.  Тесты OLE DB соответствия (включая проверка на совместимость с ADO), чтобы убедиться, что поставщик соответствует стандарту уровня 0 для поставщиков OLE DB. (Описание уровня 0, выполните поиск «OLE DB уровня 0 проверка на совместимость с» в [Руководство программиста OLE DB](http://go.microsoft.com/fwlink/p/?linkid=121548). Эти тесты и соответствующей документации входящих в состав Visual C++ в пакет SDK для доступа к данным. Эти тесты также помогают убедиться, что поставщик хорошо работает при сборке другими [поставщиками услуг](../../data/oledb/ole-db-resource-pooling-and-services.md) и особенно полезны при изменении или добавлении параметров. Дополнительные сведения о тестах соответствия см. в файле Readme в пакете SDK доступа данных, который находится на одном из дисков Visual Studio.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)