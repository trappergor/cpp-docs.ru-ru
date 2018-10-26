---
title: Отладка поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59431204ae242ac6fab0d562740f859dc85bcd11
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081801"
---
# <a name="debugging-your-provider"></a>Отладка поставщика

Существует два способа отладки поставщика:

- Поскольку поставщики создаются в процессе, можно создать определенный код потребителя, обычно используя шаблоны потребителей OLE DB и перейти к поставщику.

- Можно использовать программу ITEST, входящий в состав Visual C++.

## <a name="to-use-the-itest-utility"></a>Использование служебной программы ITEST

1. Откройте проект поставщика.

1. На **проекты** меню, щелкните **параметры**.

1. В **страницы свойств** диалоговом окне щелкните **Отладка** вкладки.

1. В **исполняемый файл для сеанса отладки** выберите приложение ITEST.

1. Установите точки останова и выполните отладку обычным образом.

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)