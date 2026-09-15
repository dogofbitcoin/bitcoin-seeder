# The DOG Mode seed's build of bitcoin-seeder

This is `sipa/bitcoin-seeder` at commit `ff482e465ff84ea6fa276d858ccb7ef32e3355d3` (master of
2024-03-23) plus two lines in `main.cpp`. Every answer requires `NODE_DOG_MODE` (service bit 14), whatever
filter the question carried. And the filter prefix is read as `x` or `X`: resolvers such as Google Public DNS
randomize the letter case of the names they ask, and upstream reads the filter only from a lowercase `x`, so
through them a filtered lookup could come back empty. It is the binary behind `dnsseed.dogofbitcoin.org`,
operated by Dog of Bitcoin Foundation Inc under Bitcoin Core's `doc/dnsseed-policy.md`. The operating
statement, the live count and the contact are at https://seed.dogofbitcoin.org.

The whole change is the one commit on the `dogmode` branch: `git diff ff482e4..dogmode`.

Run it as the seed does:

    ./dnsseed -h dnsseed.example.org -n ns1.example.org -m contact.example.org -p 53 -a <ip> \
      -w 0x1,0x5,0x9,0x49,0x809,0x849,0xd,0x400,0x404,0x408,0x448,0xc08,0xc48,0x40c,0x4009,0x4809,0x4049,0x4849,0x4408,0x4c08

Plant a second one. One seed is a start, not a design.

## License

The upstream repository carries no license file; its files that come from early Bitcoin keep Satoshi
Nakamoto's copyright notices, and Bitcoin was released under the MIT license. The two lines this branch adds
are offered under the MIT license by the Dog of Bitcoin Foundation.
