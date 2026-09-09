# Linksys Velop Pro 7 (LN6001/MBE70) Lab

Community OpenWrt firmware for the **Linksys Velop Pro 7**, hardware identifiers
**LN6001 / MBE70WRT**. This is not an official Linksys or OpenWrt image.

## 日本語

Linksys Velop Pro 7（LN6001 / MBE70WRT）向けのコミュニティ版 OpenWrt
ファームウェアです。Linksys または OpenWrt の公式イメージではありません。

### ビルド情報

| 項目 | 内容 |
| --- | --- |
| 製品 | Linksys Velop Pro 7 |
| LuCI のモデル表示 | Linksys LN6001 / MBE70WRT |
| アーキテクチャ | ARMv8 / AArch64 |
| ターゲット | `qualcommbe/ipq95xx` |
| OpenWrt | `SNAPSHOT r0-4387a153c4` |
| LuCI | `0.260709.71895` |
| Linux カーネル | `6.18.44` |
| ビルド元コミット | `ba5ad01a16679ed00a517c2c4da8490eab2c834a` |

### ファームウェア

- ファイル：[`firmware/FW_LN6001_v25.12.26090921_release.img`](firmware/FW_LN6001_v25.12.26090921_release.img)
- サイズ：`47,529,952` bytes
- SHA-256：`0d4074e2e07b4b22db920f7ede1e36c0abbc698ac7c0ab9c086fbfb1f27e6ffd`

インストール前にダウンロードしたファイルのハッシュを確認してください。

```text
0d4074e2e07b4b22db920f7ede1e36c0abbc698ac7c0ab9c086fbfb1f27e6ffd  FW_LN6001_v25.12.26090921_release.img
```

このリリースは実機で複数回インストール確認済みです。Linksys 互換の更新形式を使用し、
Wi-Fi ファームウェア、カーネル、rootfs を非アクティブ側のスロットへ書き込みます。

### インストール

1. ルーターが **LN6001 / MBE70WRT** であり、もう一方のスロットに起動可能な純正
   ファームウェアが残っていることを確認します。
2. 必要な設定をバックアップし、PC を Ethernet で接続します。
3. Linksys 純正 Web インターフェースの手動ファームウェア更新画面を開きます。
4. `FW_LN6001_v25.12.26090921_release.img` を選択し、**設定を保持する**オプションを
   無効にします。
5. 更新を開始し、再起動が完了するまで電源を切らずに待ちます。
6. PC の DHCP リースを更新し、[http://192.168.1.1/](http://192.168.1.1/) を開きます。
7. CPE 底面ラベルに記載されたパスフレーズを使って root としてログインし、
   root パスワードを変更します。
8. **ネットワーク → 無線**で国コード、チャンネル、帯域幅、送信出力を確認します。

Wi-Fi のパスフレーズも CPE 底面のラベルに記載されています。

### 別スロットへ戻す

LN6001 は、起動を 3 回中断すると通常は別のファームウェアスロットを選択します。

1. 電源を入れ、約 5 秒後に切ります。
2. この操作を合計 3 回行います。
3. 4 回目は電源を入れたまま数分待ちます。
4. Ethernet の DHCP リースを更新し、純正 Web インターフェースへ接続します。

### 補足

- このイメージは **LN6001 / MBE70WRT 専用**です。
- 初回インストールには Linksys 純正 Web 更新機能を使用してください。raw `mtd`
  書き込みや強制 `sysupgrade` は対象外です。
- ブートローダー、パーティションテーブル、ブートローダー環境、`flash.scr` は
  イメージに含まれていません。
- OpenWrt SNAPSHOT のパッケージは継続的に更新されるため、将来のパッケージが
  Linux `6.18.44` と互換でない場合があります。

[LICENSES.md](LICENSES.md) に記載された各コンポーネントのライセンスに基づき、
現状有姿で提供されます。

---

## English

### Build information

| Item | Value |
| --- | --- |
| Product | Linksys Velop Pro 7 |
| Model reported by LuCI | Linksys LN6001 / MBE70WRT |
| Architecture | ARMv8 / AArch64 |
| Target | `qualcommbe/ipq95xx` |
| OpenWrt | `SNAPSHOT r0-4387a153c4` |
| LuCI | `0.260709.71895` |
| Linux kernel | `6.18.44` |
| Source commit | `ba5ad01a16679ed00a517c2c4da8490eab2c834a` |

### Firmware

- File: [`firmware/FW_LN6001_v25.12.26090921_release.img`](firmware/FW_LN6001_v25.12.26090921_release.img)
- Size: `47,529,952` bytes
- SHA-256: `0d4074e2e07b4b22db920f7ede1e36c0abbc698ac7c0ab9c086fbfb1f27e6ffd`

Verify the downloaded image before installing it:

```text
0d4074e2e07b4b22db920f7ede1e36c0abbc698ac7c0ab9c086fbfb1f27e6ffd  FW_LN6001_v25.12.26090921_release.img
```

This release has been installed and tested on the device several times. It uses
the Linksys-compatible update format and writes the Wi-Fi firmware, kernel, and
root filesystem to the inactive slot.

### Installation

1. Confirm that the router is an **LN6001 / MBE70WRT** and that the other slot
   still contains bootable stock firmware.
2. Back up any settings you need and connect the computer by Ethernet.
3. Open the manual firmware-update page in the Linksys stock web interface.
4. Select `FW_LN6001_v25.12.26090921_release.img` and disable **Keep settings**.
5. Start the update and keep the router powered on until it finishes rebooting.
6. Renew the computer's DHCP lease and open
   [http://192.168.1.1/](http://192.168.1.1/).
7. Sign in as root using the passphrase printed on the CPE's bottom label, then
   change the root password.
8. Review the country code, channel, channel width, and transmit power under
   **Network → Wireless**.

The Wi-Fi passphrase is also printed on the CPE's bottom label.

### Returning to the other slot

The LN6001 normally selects the other firmware slot after three interrupted
boot attempts.

1. Power the router on, wait about five seconds, then power it off.
2. Repeat this sequence three times in total.
3. On the fourth power-on, leave the router running for several minutes.
4. Renew the Ethernet DHCP lease and connect to the stock web interface.

### Notes

- This image is for the **LN6001 / MBE70WRT only**.
- Use the Linksys stock web updater for the initial installation. Raw `mtd`
  writes and forced `sysupgrade` are outside this procedure.
- The image does not contain a bootloader, partition table, bootloader
  environment, or `flash.scr`.
- OpenWrt SNAPSHOT package repositories move continuously, so future packages
  may not remain compatible with Linux `6.18.44`.

See [LICENSES.md](LICENSES.md). The firmware is provided as-is under the
licenses of its included components.
