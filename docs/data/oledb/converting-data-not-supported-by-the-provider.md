---
title: Преобразование данных, не поддерживаемых поставщиком
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e60f6cd4f7dca1ed3e176cabefc42f69946436a4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033843"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Преобразование данных, не поддерживаемых поставщиком

Если потребитель запрашивает тип данных, который не поддерживается поставщиком, код шаблона поставщика OLE DB `IRowsetImpl::GetData` вызывает Msdadc.dll для преобразования типа данных.

Если реализовать интерфейс наподобие `IRowsetChange` , нуждающейся в преобразовании данных, вы можете вызвать Msdaenum.dll для выполнения преобразования. Используйте `GetData`, определенный в Atldb. h, в качестве примера.

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)