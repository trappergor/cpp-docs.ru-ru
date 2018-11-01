---
title: Преобразование данных, не поддерживаемых поставщиком
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: a53781f71a55dfb07dc996e5e25644d9337e4c63
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473447"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Преобразование данных, не поддерживаемых поставщиком

Если потребитель запрашивает тип данных, который не поддерживается поставщиком, код шаблона поставщика OLE DB `IRowsetImpl::GetData` вызывает Msdadc.dll для преобразования типа данных.

Если реализовать интерфейс наподобие `IRowsetChange` , нуждающейся в преобразовании данных, вы можете вызвать Msdaenum.dll для выполнения преобразования. Используйте `GetData`, определенный в Atldb. h, в качестве примера.

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)