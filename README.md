BabaScript
==========
BabaScript is a script language which runs on @takumibaba


Installation
------------

    % gem install babascript


Usage
-----

### BabaScript interpreter

    % baba --help

oneline

    % baba -e "月曜にかず助に行くので、出欠をとってください"


sample.bb
```ruby
if 0 < Time.now.hour and Time.now.hour < 5
  もう寝よう！！
else
  意識を高めろ！！
end
```

    % baba sample.bb


### embed BabaScript into Ruby

```ruby
require 'rubygems'
require 'babascript'

BabaScript.baba do
  起きてください
end
```

```ruby
BabaScript.baba do
  アイス買ってきてよ("#{rand(10)}本")
end
```

### switch BABA
BabaScriptはジョブ通知に[Linda](https://gihtub.com/shokai/linda-base)を使っています。
環境変数BABAのデフォルト値は"takumibaba"で、彼のジョブは http://linda.masuilab.org/takumibaba/notifications で確認できます。

    % export BABA=shokai

環境変数BABAを"shokai"に切り替えると、以後のジョブの通知先が http://linda.masuilab.org/shokai/notifications になります。


Test
----

### Install Dependencies

    % gem install bundler
    % bundle install

### Manual Test

Start VM

    % BABA=test bundle exec bin/baba-vm

Run samples

    % BABA=test bundle exec ruby samples/sample.rb

### Unit Test

    % bundle exec rake test


Contributing
------------
1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
