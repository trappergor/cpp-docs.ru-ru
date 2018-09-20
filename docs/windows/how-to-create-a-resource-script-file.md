---
title: 'Практическое: Создание файла описания ресурсов (C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32258a05cade33f20546acfc02b98370ada2b073
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387137"
---
# <a name="how-to-create-a-resource-script-file-c"></a>Практическое: Создание файла описания ресурсов (C++)

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

[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Редакторы ресурсов](../windows/resource-editors.md)