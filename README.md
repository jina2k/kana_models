Image/handwriting recognition AI made for recognizing hiragana/katakana characters.

Split out to several categories to improve accuracy, was made by referencing Japan's AIST ETLCDB: http://etlcdb.db.aist.go.jp/

These models are shared under the Apache License 2.0. Images can not be shared as they are under AIST's domain.

Hiragana accuracy - around 85%?<br>
Katakana accuracy - around 70%?

Models take in grayscale images, trained on images with black backgrounds and white characters.

Hiragana/Katakana was separated as follows:

hira_label_model - 3 classes, of which are matched with either A, B, or C<br>
A- tried to separate based off a line on top<br>
B- line on left hand side / majority of the character being on the left side<br>
C- misc

kata_label_model - 4 classes, of which are matched with either A, B, C, or D<br>
A- line on top<br>
B- misc<br>
C- downward curve going to left side, with a line on top as well<br>
D- downward curve going left side, without lines on top


tldr; classes as separated below: hira first then kata

labels = ['A', 'B', 'C']<br>
zerolabels =  ['あ', 'う', 'え', 'お', 'き', 'こ', 'さ', 'す', 'せ', 'そ', 'ち', 'つ', 'て', 'ま', 'ら', 'る', 'ろ', 'を']<br>
onelabels = ['い', 'か', 'け', 'し', 'た', 'な', 'に', 'ね', 'は', 'ほ', 'み', 'む', 'も', 'ゆ', 'り', 'れ', 'わ']<br>
twolabels = ['く', 'と', 'ぬ', 'の', 'ひ', 'ふ', 'へ', 'め', 'や', 'よ', 'ん']

labels = ['A', 'B', 'C', 'D']<br>
zerolabels = ['エ', 'オ', 'カ', 'キ', 'コ', 'ス', 'セ', 'チ', 'テ', 'ナ', 'ニ', 'ヌ', 'ネ', 'ホ', 'マ', 'ミ', 'モ', 'ヤ', 'ユ', 'ヨ', 'ロ']<br>
onelabels = ['イ', 'ト', 'ハ', 'ヒ', 'ヘ', 'ム', 'ル', 'レ']<br>
twolabels = ['ア', 'ウ', 'ク', 'ケ', 'サ', 'タ', 'フ', 'ラ', 'ワ', 'ヲ']<br>
threelabels = ['シ', 'ソ', 'ツ', 'ノ', 'メ', 'リ', 'ン']

Personal note: Since Google released their handwriting AI (https://developers.google.com/ml-kit/vision/digital-ink-recognition), these models are just something that I made in my free time. Probably would be a better idea to integrate with this ML Kit instead. Reference to Flutter version of Google's ML Kit AI: https://pub.dev/packages/google_mlkit_digital_ink_recognition