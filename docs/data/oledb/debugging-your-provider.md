---
title: "Отладка поставщика | Документы Microsoft"
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
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c5dcca9888f22aadb629bcd79a5eb73b39cddcfa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="debugging-your-provider"></a>Отладка поставщика
Существует два способа отладки поставщика:  
  
-   Поскольку поставщики создаются в процессе, можно создать определенный код потребителя, обычно используя шаблоны потребителя OLE DB и перейти к поставщику.  
  
-   Можно использовать служебную программу ITEST, входящий в состав Visual C++.  
  
### <a name="to-use-the-itest-utility"></a>Использование служебной программы ITEST  
  
1.  Откройте проект поставщика.  
  
2.  На **проекты** меню, нажмите кнопку **параметры**.  
  
3.  В **страницы свойств** диалоговое окно, нажмите кнопку **отладки** вкладки.  
  
4.  В **исполняемый файл для сеанса отладки** выберите приложение ITEST.  
  
5.  Установите точки останова и выполните отладку обычным образом.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)