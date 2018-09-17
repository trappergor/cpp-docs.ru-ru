---
title: -ALLOWBIND | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce0a33ebb0b8b9ba34ac241c8335e9524dec08b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715578"
---
# <a name="allowbind"></a>/ALLOWBIND

Указывает, можно ли привязать библиотеку DLL.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Примечания

**Параметра/ALLOWBIND** параметр устанавливает бит в заголовке DLL, указывающий Bind.exe, что изображение может быть привязан. Привязки можно разрешить изображения загружаются быстрее, если загрузчик не имеет повторное размещение и выполнение адресную привязку для каждой библиотеки DLL, на которую указывает ссылка. Вы можете не захотеть библиотеку DLL, если она подписана цифровой подписью, подпись недействительной привязки. Привязки не оказывает влияния технологию address space макета randomization (ASLR) включен для образа с помощью **/DYNAMICBASE** в версиях Windows, поддерживать ASLR.

Используйте **/ALLOWBIND:NO** для предотвращения Bind.exe привязка библиотеки DLL.

Дополнительные сведения см. в разделе [параметра/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) параметр компоновщика.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)