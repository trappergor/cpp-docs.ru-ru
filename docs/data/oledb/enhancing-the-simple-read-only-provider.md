---
title: Усовершенствование простого поставщика только для чтения
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: d61f24a9a9abffe836a7f11bd5d1517fddf97fe7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034080"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Усовершенствование простого поставщика только для чтения

В этом разделе показано, как улучшить [простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) создан в предыдущем разделе. `IRowsetLocateImpl` Создает реализацию `IRowsetLocate` интерфейс и добавляет поддержку закладку для вас.

Если у вас есть действующий поставщик, может потребоваться расширить его возможности для обеспечения обновления, обработки транзакций или повышения производительности алгоритма выборки строк. Усовершенствования, реализованные в поставщик, предполагает Добавление интерфейса в существующий объект COM.

В примере в следующих разделах улучшает механизм извлечения строк, добавив `IRowsetLocate` интерфейс `CAgentRowset`. В подразделах показано, как для:

- [Сделать RCustomRowset наследовать от IRowsetLocate](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).

- [Динамически определять столбцы, возвращенные объекту-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>См. также

[Создание простого поставщика только для чтения](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
