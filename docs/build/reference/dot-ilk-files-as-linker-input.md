---
title: ILK-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 6c0eb5627d7dd1b414351dc65685c0c5071d249e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422511"
---
# <a name="ilk-files-as-linker-input"></a>ILK-файлы в качестве входных файлов компоновщика

При связывании постепенно, ссылка обновляет состояние ILK-файл, созданный им во время первого инкрементной компоновки. Этот файл имеет такое же базовое имя файла .exe или DLL-файл, и имеет расширение .ilk. Во время последовательных инкрементных компоновок обновление ссылки в ILK-файл. Если отсутствует ILK-файл, ссылка выполняет полную компоновку и создает новый ILK-файл. Если в ILK-файл не работает, LINK выполняет недобавочная компоновку. Дополнительные сведения о инкрементную компоновку, см. в разделе [инкрементная компоновка (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) параметр.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
