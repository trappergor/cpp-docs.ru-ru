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
ms.openlocfilehash: 4cb7e5a3627d865e2f2193dee096c72cced75f5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273200"
---
# <a name="allowbind"></a>/ALLOWBIND

Указывает, можно ли привязать библиотеку DLL.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Примечания

**Параметра/ALLOWBIND** параметр устанавливает бит в заголовке DLL, указывающий Bind.exe, что изображение может быть привязан. Привязки можно разрешить изображения загружаются быстрее, если загрузчик не имеет повторное размещение и выполнение адресную привязку для каждой библиотеки DLL, на которую указывает ссылка. Вы можете не захотеть библиотеку DLL, если она подписана цифровой подписью, подпись недействительной привязки. Привязки не оказывает влияния технологию address space макета randomization (ASLR) включен для образа с помощью **/DYNAMICBASE** в версиях Windows, поддерживать ASLR.

Используйте **/ALLOWBIND:NO** для предотвращения Bind.exe привязка библиотеки DLL.

Дополнительные сведения см. в разделе [параметра/ALLOWBIND](allowbind-prevent-dll-binding.md) параметр компоновщика.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](editbin-options.md)
