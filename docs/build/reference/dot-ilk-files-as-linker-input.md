---
title: ILK-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 252c1cd6e17346954fce7ebf16134246da76ba57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293853"
---
# <a name="ilk-files-as-linker-input"></a>ILK-файлы в качестве входных файлов компоновщика

При связывании постепенно, ссылка обновляет состояние ILK-файл, созданный им во время первого инкрементной компоновки. Этот файл имеет такое же базовое имя файла .exe или DLL-файл, и имеет расширение .ilk. Во время последовательных инкрементных компоновок обновление ссылки в ILK-файл. Если отсутствует ILK-файл, ссылка выполняет полную компоновку и создает новый ILK-файл. Если в ILK-файл не работает, LINK выполняет недобавочная компоновку. Дополнительные сведения о инкрементную компоновку, см. в разделе [инкрементная компоновка (/ INCREMENTAL)](incremental-link-incrementally.md) параметр.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](link-input-files.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
