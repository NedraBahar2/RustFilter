# RustFilter

    struct FilterCondition {
        target_value: i32,
    }
    
    impl FilterCondition {
        fn is_match(&self, item: &i32) -> bool {
            *item == self.target_value
        }
    }
    
    fn custom_filter(collection: Vec<i32>, filter_condition: &FilterCondition) -> Vec<i32> {
        collection
            .into_iter()
            .filter(|item| filter_condition.is_match(item))
            .collect()
    }
    
    fn main() {
        let numbers = vec![1, 2, 3, 4, 5];
        let filter_condition = FilterCondition { target_value: 3 };
    
        let filtered_numbers = custom_filter(numbers, &filter_condition);
    
        println!("Filtered Numbers: {:?}", filtered_numbers);
    }
