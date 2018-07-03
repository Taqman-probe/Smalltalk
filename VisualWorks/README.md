QRCodeForVisualWorks can create Depth1Image instanse of QRCode.
Examples of Simple usage is as follows

QRCodeGenerator getImage: 'Hello world. Hello QRCodeGenerator.'

The errorCorrectionLevel is specified with M.
The quietZone is specified with 4 pixcel.
The mode(Digit, AlphaNumeric, Kanji or EightBit) is decided by data.
The version is decided minimal enough.
You can specify these properties.
To decode multi byte characters, you must specify encoding.
To decode Non-printable characters, you can pass a ByteArray instance directly.

Examples of advanced usage is as follows.

| qr |
qr := QRCodeGenerator new.
qr data: 'Hello world. Hello QRCodeGenerator.'.
qr errorCorrectionLevel: #Q.
qr mode: #eightBit.
qr version: 5.
qr quietZone: 0.
ScheduledWindow new component: ((qr getImage) magnifiedBy: 6@6); open
