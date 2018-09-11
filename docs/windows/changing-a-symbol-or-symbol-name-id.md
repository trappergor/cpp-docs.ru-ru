---
title: Изменение символа или символьного имени (идентификатор) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols [C++], names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b80c854d144f0f2010d1482a03f692062ea81ef
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315903"
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>Изменение символа или символьного имени (идентификатор)

При создании нового ресурса или объекта ресурса среда разработки присваивает ему имя символа, заданное по умолчанию, например, IDD_DIALOG1. Можно использовать [окно "Свойства"](/visualstudio/ide/reference/properties-window) Чтобы изменить имя символа по умолчанию или изменить имя любого символа, уже связан с ресурсом.

### <a name="to-change-a-resources-symbol-name"></a>Изменение имени символа ресурса

1. В [представление ресурсов](../windows/resource-view-window.md), выберите ресурс.

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В **свойства** окно, введите новое имя символа или выберите из списка существующих символов в **идентификатор** поле.

   При вводе нового имени символа ему автоматически присваивается значение.

Можно использовать [символы ресурсов-диалоговое окно](../windows/resource-symbols-dialog-box.md) Чтобы изменить имена символов, в настоящее время не назначен ресурс. Дополнительные сведения см. в разделе [изменение неназначенных символов](../windows/changing-unassigned-symbols.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Ограничения для имен символов](../windows/symbol-name-restrictions.md)  
[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)