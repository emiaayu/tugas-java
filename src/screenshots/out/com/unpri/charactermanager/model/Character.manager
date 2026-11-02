package com.unpri.charactermanager.model;

import java.util.ArrayList;

public class CharacterManager {

    private ArrayList<Character> characters = new ArrayList<>();

    // Tambah karakter. Gagal (false) kalau null atau nama sudah ada.
    public boolean addCharacter(Character character) {
        if (character == null) {
            return false;
        }
        if (characters.contains(character)) { // pakai equals() -> cek nama
            return false;
        }
        return characters.add(character);
    }

    // Hapus berdasarkan nama. true kalau ada yang terhapus.
    public boolean removeCharacter(String name) {
        Character found = findByName(name);
        if (found == null) {
            return false;
        }
        return characters.remove(found);
    }

    // Cari berdasarkan nama. Return null kalau tidak ketemu.
    public Character findByName(String name) {
        for (Character c : characters) {
            if (c.getName().equalsIgnoreCase(name)) {
                return c;
            }
        }
        return null;
    }

    // Cari semua karakter dengan tipe tertentu.
    public ArrayList<Character> findByType(CharacterType type) {
        ArrayList<Character> result = new ArrayList<>();
        for (Character c : characters) {
            if (c.getType() == type) {
                result.add(c);
            }
        }
        return result;
    }

    // Defensive copy: yang dikembalikan salinan, bukan list aslinya.
    public ArrayList<Character> getAllCharacters() {
        return new ArrayList<>(characters);
    }

    public int getTotalCharacters() {
        return characters.size();
    }

    // Rata-rata level. Daftar kosong -> 0.0 (hindari bagi nol).
    public double getAverageLevel() {
        if (characters.isEmpty()) {
            return 0.0;
        }
        int sum = 0;
        for (Character c : characters) {
            sum += c.getLevel();
        }
        return (double) sum / characters.size();
    }

    public int countByType(CharacterType type) {
        int count = 0;
        for (Character c : characters) {
            if (c.getType() == type) {
                count++;
            }
        }
        return count;
    }
}