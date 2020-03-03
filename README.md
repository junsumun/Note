# note


        WebClient webClient = WebClient.create("http://localhost:8080");

        webClient.post()
                .uri(uriBuilder -> uriBuilder
                        .path("/chat/room")
                        .queryParam("name", "TESTING")
                        .build())
                .bodyValue("Test")
                .retrieve()
                .bodyToMono(String.class)
                .subscribe(System.out::println);
