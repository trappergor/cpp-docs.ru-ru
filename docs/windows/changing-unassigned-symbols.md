---
title: Изменение или удаление неназначенных символов
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.unassigned
helpviewer_keywords:
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
ms.assetid: b6abee4a-3c24-4697-a166-fe6a86cad35f
ms.openlocfilehash: 47cc3d7a387092afe77fdbcf4bbdb6d085eeda25
ms.sourcegitcommit: 966e4466f10c93fc12faf33d28e03b39489423fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2019
ms.locfileid: "55987018"
---
# <a name="changing-or-deleting-unassigned-symbols"></a>Изменение или удаление неназначенных символов

При работе в [символы ресурсов-диалоговое окно](../windows/resource-symbols-dialog-box.md), можно редактировать или удалять существующие символы, которые не назначены ресурсу или объекту.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="to-change-an-unassigned-symbol"></a>Изменение неназначенного символа

1. В **имя** , выберите неназначенный символ и выберите **изменение**.

1. Измените имя символа или другие значения в соответствующих полях в **Изменение символа** диалоговое окно.

   > [!NOTE]
   > Чтобы изменить символ, который *является* назначен ресурсу или объекту, необходимо использовать редактор ресурсов или **свойства** окно. Дополнительные сведения см. в разделе [Изменение символа или символьного имени](../windows/changing-a-symbol-or-symbol-name-id.md).

## <a name="to-delete-an-unassigned-unused-symbol"></a>Удаление неназначенного (неиспользуемого) символа

В [символы ресурсов-диалоговое окно](../windows/resource-symbols-dialog-box.md), выберите символ, который требуется удалить и выберите пункт **удалить**.

   > [!NOTE]
   > Перед удалением неиспользуемого символа в файле ресурсов убедитесь в том, что он не используется где-либо в программе или в файлах ресурсов, включаемых во время компиляции.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Просмотр символов ресурсов](../windows/viewing-resource-symbols.md)<br/>
[Ограничения для имен символов](../windows/symbol-name-restrictions.md)<br/>
[Ограничения для символьных значений](../windows/symbol-value-restrictions.md)<br/>
[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)