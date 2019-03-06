---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 8f59cc83c06bbaaccba911c44835247253cb264b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416895"
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
