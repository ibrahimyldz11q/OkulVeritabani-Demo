SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Veritabanı: `okul`
--

-- --------------------------------------------------------

--
-- Tablo için tablo yapısı `bölümler`
--

CREATE TABLE `bölümler` (
  `id` int(11) NOT NULL,
  `bolum_ad` varchar(50) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Tablo döküm verisi `bölümler`
--

INSERT INTO `bölümler` (`id`, `bolum_ad`) VALUES
(1, 'Bilisim Teknolojileri'),
(2, 'Muhasebe ve Finansman');

-- --------------------------------------------------------

--
-- Tablo için tablo yapısı `dersler`
--

CREATE TABLE `dersler` (
  `id` int(11) NOT NULL,
  `ders_ad` varchar(50) DEFAULT NULL,
  `ders_kredi` int(10) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Tablo döküm verisi `dersler`
--

INSERT INTO `dersler` (`id`, `ders_ad`, `ders_kredi`) VALUES
(1, 'Veri Tabani', 4),
(2, 'Maliyet Muhasebesi', 5);

-- --------------------------------------------------------

--
-- Tablo için tablo yapısı `ögrenciler`
--

CREATE TABLE `ögrenciler` (
  `ögrenci_no` int(12) NOT NULL,
  `ad` varchar(50) NOT NULL,
  `soyad` varchar(50) NOT NULL,
  `bolum_no` int(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Tablo döküm verisi `ögrenciler`
--

INSERT INTO `ögrenciler` (`ögrenci_no`, `ad`, `soyad`, `bolum_no`) VALUES
(1912403050, 'Ibrahim ', 'Yildiz', 1),
(1912403060, 'Selin', 'Yildiz', 2);

-- --------------------------------------------------------

--
-- Tablo için tablo yapısı `ögrenci_ders`
--

CREATE TABLE `ögrenci_ders` (
  `id` int(11) NOT NULL,
  `ogrenci_no` int(12) NOT NULL,
  `ders_no` int(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Tablo döküm verisi `ögrenci_ders`
--

INSERT INTO `ögrenci_ders` (`id`, `ogrenci_no`, `ders_no`) VALUES
(1, 1912403050, 1),
(2, 1912403060, 2);

--
-- Dökümü yapılmış tablolar için indeksler
--

--
-- Tablo için indeksler `bölümler`
--
ALTER TABLE `bölümler`
  ADD PRIMARY KEY (`id`);

--
-- Tablo için indeksler `dersler`
--
ALTER TABLE `dersler`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `ders_ad` (`ders_ad`);

--
-- Tablo için indeksler `ögrenciler`
--
ALTER TABLE `ögrenciler`
  ADD PRIMARY KEY (`ögrenci_no`),
  ADD KEY `bolum_no` (`bolum_no`);

--
-- Tablo için indeksler `ögrenci_ders`
--
ALTER TABLE `ögrenci_ders`
  ADD PRIMARY KEY (`id`),
  ADD KEY `ogrenci_no` (`ogrenci_no`),
  ADD KEY `ders_no` (`ders_no`);

--
-- Dökümü yapılmış tablolar için AUTO_INCREMENT değeri
--

--
-- Tablo için AUTO_INCREMENT değeri `bölümler`
--
ALTER TABLE `bölümler`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

--
-- Tablo için AUTO_INCREMENT değeri `dersler`
--
ALTER TABLE `dersler`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

--
-- Tablo için AUTO_INCREMENT değeri `ögrenci_ders`
--
ALTER TABLE `ögrenci_ders`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

--
-- Dökümü yapılmış tablolar için kısıtlamalar
--

--
-- Tablo kısıtlamaları `ögrenciler`
--
ALTER TABLE `ögrenciler`
  ADD CONSTRAINT `ögrenciler_ibfk_1` FOREIGN KEY (`bolum_no`) REFERENCES `bölümler` (`id`) ON DELETE CASCADE ON UPDATE CASCADE;

--
-- Tablo kısıtlamaları `ögrenci_ders`
--
ALTER TABLE `ögrenci_ders`
  ADD CONSTRAINT `ögrenci_ders_ibfk_1` FOREIGN KEY (`ogrenci_no`) REFERENCES `ögrenciler` (`ögrenci_no`),
  ADD CONSTRAINT `ögrenci_ders_ibfk_2` FOREIGN KEY (`ders_no`) REFERENCES `dersler` (`id`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
