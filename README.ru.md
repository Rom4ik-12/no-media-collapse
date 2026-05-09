# no-media-collapse

[English](README.md)

Пользовательский модуль для загрузчика
[illogical-impulse-plugins](https://github.com/Rom4ik-12/illogical-impulse-plugins).
Сворачивает медиа-секцию бара до её естественной ширины, когда ничего
не играет, чтобы пустая плашка «Нет медиа» не занимала место.

## Что делает

Переключает две строки в `modules/ii/bar/BarContent.qml`:

```qml
// выкл (дефолт системы — фиксированная широкая)
implicitWidth: root.centerSideModuleWidth

// вкл (этот модуль — сворачивается без трека)
implicitWidth: (root.useShortenedForm < 2 &&
                MprisController.activePlayer?.trackTitle?.length > 0)
              ? root.centerSideModuleWidth
              : leftCenterGroup.naturalImplicitWidth
```

Включи — получишь авто-схлопывание; выключи — слот всегда полной ширины
вне зависимости от того, играет ли что-то.

## Установка

Вставь ссылку в Settings → Modules → поле установки:

```
https://github.com/Rom4ik-12/no-media-collapse/releases/latest/download/no-media-collapse.qsmod
```

Или скачай `.qsmod` со
[страницы релизов](https://github.com/Rom4ik-12/no-media-collapse/releases) и
кинь его в "Выбрать файл…".

## Требования

- Загрузчик illogical-impulse-plugins **v1.4** или новее
  (указан `requiresLoader: "1.4"`).
