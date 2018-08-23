---
title: 'Практическое: Создание файла описания ресурсов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files, creating
- .rc files, creating
- resource script files, creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b07efbd4f1434992c76de2b7e959f4578d60096
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608741"
---
# <a name="how-to-create-a-resource-script-file"></a>Практическое руководство. Создание файла описания ресурсов

> [!NOTE]
> **Редактора ресурсов** недоступна в выпусках Express.
>
> Этот материал относится к классическим приложениям Windows. В проектах на языках .NET файлы описания ресурсов не используются. Дополнительные сведения см. в разделе [Файлы ресурсов](../windows/resource-files-visual-studio.md).

### <a name="to-create-a-new-resource-script-rc-file"></a>Создание файла описания ресурсов (RC)

1. Поместить фокус на папку существующего проекта в **обозревателе решений**, например `MyProject`.

   > [!NOTE]
   > Не перепутайте папку проекта с папкой решения в **обозревателе решений**. Если поместить фокус на **решение** папки, выбранные в **Добавление нового элемента** диалоговое окно (в шаге 3) будет отличаться.

2. В меню **Проект** выберите пункт **Добавить новый элемент**.

3. В диалоговом окне **Добавление нового элемента** выберите папку **Visual C++** , а затем выберите в правой области **Файл ресурсов (.rc)** .

4. Укажите имя файла описания ресурсов в текстовом поле **Имя** и нажмите кнопку **Открыть**.

Теперь можно [создать](../windows/how-to-create-a-resource.md) ресурсы и добавить их в RC-файл.

> [!NOTE]
> Файл описания ресурсов (RC) можно добавить только в существующий проект, загруженный в интегрированную среду разработки Visual Studio. Нельзя создать автономный RC-файл (за пределами проекта). [Шаблоны ресурсов](../windows/how-to-use-resource-templates.md) (RCT-файлы) можно создать в любой момент.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редакторы ресурсов](../windows/resource-editors.md)