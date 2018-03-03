---
title: "Требования к драйверам ODBC динамических подмножеств данных | Документы Microsoft"
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
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c444cd8e8d13cca7d891dba92e881b8ca167bbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-driver-requirements-for-dynasets"></a>Требования динамических подмножеств данных к драйверу ODBC
В классы баз данных MFC ODBC динамические подмножества данных, наборы записей с динамическими свойствами. они синхронизация с источником данных, определенным образом. Динамические подмножества данных MFC (но не наборы записей последовательного доступа) требуют соответствия уровня 2 API драйвера ODBC. Если драйвер для вашего [источника данных](../../data/odbc/data-source-odbc.md) соответствует API уровня 1 задано, можно по-прежнему использовать обновляемые и только для чтения моментальные снимки и наборы последовательного доступа, но не динамических подмножеств данных. Тем не менее драйвер уровня 1 может поддерживать динамические подмножества данных, если он поддерживает расширенную выборки и управляемые набором ключей курсоры.  
  
 В терминологии ODBC подмножества и моментальные снимки называются курсоров. Курсор — это механизм, используемый для отслеживания его позиции в наборе записей. Дополнительные сведения о требованиях к драйверам динамических подмножеств данных см. в разделе [динамический набор](../../data/odbc/dynaset.md). Дополнительные сведения о курсорах см. в разделе [Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK в документации MSDN.  
  
> [!NOTE]
>  Для обновляемых наборов записей драйвер ODBC должен поддерживать инструкции позиционированного обновления или **:: SQLSetPos** функции ODBC API. Если оба поддерживаются, MFC использует **:: SQLSetPos** для повышения эффективности. Кроме того для моментальных снимков, можно использовать библиотеку курсора, которая поддерживает необходимые обновляемые снимки (статические курсоры и инструкций позиционированного обновления).  
  
## <a name="see-also"></a>См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)